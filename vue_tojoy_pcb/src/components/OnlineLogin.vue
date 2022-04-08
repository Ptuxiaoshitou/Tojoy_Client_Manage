<template>
    <div id="magicalDragScene" class="mc-root mc-ui-absolute-pane">
        <el-card>
            <el-tabs value="first" @tab-click="_tabClick">
                <el-tab-pane name="first" label="选项1">
                    <div style="text-align: center;height: 50px">
                    </div>
                    <el-form :model="ruleForm" status-icon :rules="rules" ref="ruleForm" label-width="100px" class="demo-ruleForm">
                    <el-form-item label="账号" prop="user">
                        <el-input type="text" v-model="ruleForm.user" autocomplete="off"></el-input>
                    </el-form-item>
                    <el-form-item label="密码" prop="pass">
                        <el-input type="password" v-model="ruleForm.pass" autocomplete="off"></el-input>
                    </el-form-item>
                <!--      <el-form-item label="年龄" prop="age">-->
                <!--        <el-input v-model.number="ruleForm.age"></el-input>-->
                <!--      </el-form-item>-->
                    <el-form-item>
                        <el-button type="primary" @click="submitForm('ruleForm')">提交</el-button>
                        <el-button @click="resetForm('ruleForm')">重置</el-button>
                    </el-form-item>
                    </el-form>
                </el-tab-pane>
                <el-tab-pane name="second" label="选项2">
                    <el-input></el-input>
                        <el-input></el-input>
                        <el-image style="width: 30%; height: 50px;" src="img.jpg"></el-image>
                    <el-input></el-input>
                    <el-button @click="gotolink" class="btn btn-success" type="primary" >点击跳转页面</el-button>     
                    <el-button @click="onSubmit">立即创建</el-button>
                    <el-link>文字链接</el-link>
                    <el-link>文字链接</el-link>
                </el-tab-pane>
                <el-tab-pane name="third" label="选项3">
                </el-tab-pane>
            </el-tabs>
        </el-card>
    </div>
</template>
<script>
  // import axios from 'axios'
  export default {
    name: "login",
  data() {
    var validatePass = (rule, value, callback) => {
      if (value === '') {
        callback(new Error('请输入账户'));
      } else {
        if (this.ruleForm.pass !== '') {
          this.$refs.ruleForm.validateField('pass');
        }
        callback();
      }
    };
    var validatePass2 = (rule, value, callback) => {
      if (value === '') {
        callback(new Error('请输入密码'));
      } else {
        callback();
      }
    };
    return {
      ruleForm: {
        user: '',
        pass: '',
      },
      rules: {
        user: [
          { validator: validatePass, trigger: 'blur' }
        ],
        pass: [
          { validator: validatePass2, trigger: 'blur' }
        ],
        // age: [
        //   { validator: checkAge, trigger: 'blur' }
        // ]
      },
      isLogin:false
    };
  },
  methods: {
    submitForm(formName) {
      this.$message.success("登录成功!!!");
      this.$router.push({path: "/user"});
    },
    resetForm(formName) {
      this.$refs[formName].resetFields();
    }
  }
  }
</script>

<style scoped>
.el-card{
    margin-left:57px;
    margin-right:px;
    width: 840px;
    height: 466px;
    margin-bottom: 20px;
}
 body{
    margin: 0;
  }
  #login-container{
    width: 400px;
    height: 290px;
    background: #e5e9f2;
    position: absolute;
    left: 50%;
    top: 50%;
    margin-left: -220px;
    margin-top: -170px;
    border-radius: 5px;
    padding-top: 40px;
    padding-right: 40px;
  }
</style>