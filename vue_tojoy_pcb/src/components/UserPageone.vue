<template>
<el-card>
    <el-card class = 'card1'>
        <span class="mc-ui-geometry-char">账户信息</span>
        
        <el-button class="mc-open-dialog-btn" @click="showDialog=true"  type="primary" >编辑资料</el-button>
        <el-dialog class="editor-data" title="编辑客户资料" :visible.sync="showDialog"> 
            <!-- :model="ruleForm" :rules="rules" ref="ruleForm" -->
            <el-form  label-width="100px" class="demo-ruleForm">  
                <el-form-item style="letter-spacing:1px;" label="公司名称：" prop="name" required>
                    <!-- v-model="ruleForm.name" -->
                    <el-col :span="10">
                        <el-input v-model="input" placeholder="请输入内容"></el-input>
                    </el-col>
                </el-form-item>
                <el-form-item  style="letter-spacing:4px;" label="联系人："  required>
                    <!-- v-model="ruleForm.name" -->
                    <el-col :span="10">
                        <el-input v-model="input1"></el-input>
                    </el-col>
                </el-form-item>
                <el-form-item  style="letter-spacing:2px;" label="QQ号码：" required> 
                    <!-- v-model="ruleForm.name" -->
                    <el-col :span="10">
                        <el-input  :disabled="true"></el-input>
                    </el-col>
                <!-- v-if -->      
                    <el-checkbox  v-model="checked_qq">修改</el-checkbox>

                </el-form-item>
                <el-form-item style="letter-spacing:1px;" label="座机电话："  required>
                    <!-- v-model="ruleForm.name" -->
                    <el-col :span="10">
                        <el-input  :disabled="true"></el-input>
                    </el-col>
                    <el-checkbox  v-model="checked_tel">修改</el-checkbox>
                </el-form-item>
                <el-form-item style="letter-spacing:1px;" label="手机号码："  required>
                    <!-- v-model="ruleForm.name" -->
                    <el-col :span="10">
                        <el-input  :disabled="true"></el-input>
                    </el-col>
                    <el-checkbox  v-model="checked_telnum">修改</el-checkbox>
                </el-form-item>
                <el-form-item style="letter-spacing:8px;" label="邮箱：" required>
                    <!-- v-model="ruleForm.name" -->
                    <el-col :span="10">
                        <el-input  :disabled="true"></el-input>
                    </el-col>
                    <el-checkbox  v-model="checked_mail">修改</el-checkbox>
                </el-form-item>
                <el-button type="primary" @click="submitForm('ruleForm')">提交</el-button>
                <el-button  @click="submitForm('ruleForm')">取消</el-button>
            </el-form>
        </el-dialog>
           
        <div class = 'account'>
            <span class="account-text">客户编号：CS2080 &emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;</span>
            <span>联系人：舒文厅&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;</span>
            <span>座机号码：0355-6969696&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;</span>
            <span>邮箱：52515685@163.com&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;</span>
        </div>
        <div class = 'account1'>
            <span >公司名称：长沙开谱仪器有限公司&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;</span>
            <span>绑定手机：1234567788&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;</span>   
            <span>手机号码：11111111111&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;</span>
            <span>QQ号码：11111111111&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;   </span>
        </div>

    </el-card>


    <el-card class = 'card2'>
        <span class="mc-ui-geometry-char1">收货地址</span>
        <span>
            <el-button class="mc-open-dialog-btn1" @click="showDialog1=true"  type="primary" >+ 新增收货地址</el-button>          
        </span>
        <el-table
                :data="tableData"
                style="width: 100%"
                height="auto"
                wight="auto">
                <el-table-column
                prop="name"
                label="联系人">
                 <template slot-scope="scope">
                    <el-popover trigger="hover" placement="top">
                        <p>姓名: {{ scope.row.name }}</p>
                        <p>住址: {{ scope.row.address }}</p>
                    <div slot="reference" class="name-wrapper">
                        <el-tag size="medium">{{ scope.row.name }}</el-tag>
                    </div>
                    </el-popover>
                </template>
                </el-table-column>
                <el-table-column
                prop="phone"
                label="联系电话">
                </el-table-column>
                <el-table-column
                prop="address"
                label="详细地址">
                </el-table-column>
                <el-table-column
                prop="operation"
                label="操作">
                    <template slot-scope="scope">
                        <el-button
                            size="mini" type="primary"
                            >默认地址</el-button>
                        <el-button
                            size="mini"
                            @click="handleEdit(scope.$index, scope.row)">修改</el-button>
                        <el-button
                            @click.native.prevent="deleteRow(scope.$index, tableData)"
                            
                            size="mini" type="danger">
                            移除
                        </el-button>
                </template>
                </el-table-column>
            </el-table>
    </el-card>


    <el-card class = 'card3'>
        <span class="mc-ui-geometry-char2">开票资料</span>
        <span>
            <el-button class="mc-open-dialog-btn2" @click="showDialog2=true"  type="primary" >+ 新增开票资料</el-button>    
        </span>
        <el-table
                :data="tableData"
                style="width: 100%"
                height="auto"
                wight = "auto">
                <el-table-column
                prop="name"
                label="开票公司名称/个人名称">
                </el-table-column>
                <el-table-column
                prop="phone"
                label="开票主体">
                </el-table-column>
                <el-table-column
                prop="address"
                label="税号">
                </el-table-column>
                <el-table-column
                prop="address"
                label="是否完善">
                </el-table-column>
                 <el-table-column
                prop="operation"
                label="操作">
                    <template slot-scope="scope">
                        <el-button
                            size="mini" type="primary"
                            >默认地址</el-button>
                        <el-button
                            size="mini"
                            @click="handleEdit(scope.$index, scope.row)">修改</el-button>
                        <el-button
                            @click.native.prevent="deleteRow(scope.$index, tableData)"
                            
                            size="mini" type="danger">
                            移除
                        </el-button>
                </template>
                </el-table-column>
            </el-table>
    </el-card>


    
    <el-card class = 'card4'>
        <span class="mc-ui-geometry-char3">开票收货地址</span>
        <span>
            <el-button class="mc-open-dialog-btn3" @click="showDialog3=true"  type="primary" >+ 新增开票地址</el-button>
        </span>
          <el-table
                :data="tableData"
                style="width: 100%"
                height="auto"
                wight="auto">
                <el-table-column
                prop="name"
                label="联系人">
                 <template slot-scope="scope">
                    <el-popover trigger="hover" placement="top">
                        <p>姓名: {{ scope.row.name }}</p>
                        <p>住址: {{ scope.row.address }}</p>
                    <div slot="reference" class="name-wrapper">
                        <el-tag size="medium">{{ scope.row.name }}</el-tag>
                    </div>
                    </el-popover>
                </template>
                </el-table-column>
                <el-table-column
                prop="phone"
                label="联系电话">
                </el-table-column>
                <el-table-column
                prop="address"
                label="详细地址">
                </el-table-column>
                <el-table-column
                prop="operation"
                label="操作">
                    <template slot-scope="scope">
                        <el-button
                            size="mini" type="primary"
                            >默认地址</el-button>
                        <el-button
                            size="mini"
                            @click="handleEdit(scope.$index, scope.row)">修改</el-button>
                        <el-button
                            @click.native.prevent="deleteRow(scope.$index, tableData)"
                            
                            size="mini" type="danger">
                            移除
                        </el-button>
                </template>
                </el-table-column>
            </el-table>
    </el-card>
</el-card>
</template>


<script>
  export default {
    name:'User',
    components:{
    },
    data() {
        return {
            showDialog: false,
            showDialog1: false,
            checked_qq: false,
            checked_tel: false,
            checked_telnum: false,
            checked_mail: false,
            input: '',
            input1: '',
            tableData: [{
                name: '王小虎',
                province: '上海',
                city: '普陀区',
                address: '上海市普陀区金沙江路 1518 弄',
                zip: 200333
                }, {
                name: '王小虎',
                province: '上海',
                city: '普陀区',
                address: '上海市普陀区金沙江路 1518 弄',
                zip: 200333
                }, {
                date: '2016-05-04',
                name: '王小虎',
                phone: '上海',
                city: '普陀区',
                address: '上海市普陀区金沙江路 1518 弄',
                zip: 200333
                }, {
                name: '王小虎',
                province: '上海',
                city: '普陀区',
                address: '上海市普陀区金沙江路 1518 弄',
                zip: 200333
                }, {
                name: '王小虎',
                province: '上海',
                city: '普陀区',
                address: '上海市普陀区金沙江路 1518 弄',
                zip: 200333
                }, {
                name: '王小虎',
                province: '上海',
                city: '普陀区',
                address: '上海市普陀区金沙江路 1518 弄',
                zip: 200333
                }, {
                name: '王小虎',
                province: '上海',
                city: '普陀区',
                address: '上海市普陀区金沙江路 1518 弄',
                zip: 200333
                }]
        };
    },
    methods: {
      handleEdit(index, row) {
        console.log(index, row);
      },

      deleteRow(index, rows) {
        rows.splice(index, 1);
    },
    }
  }

</script>
<style scoped>
 .el-card{
        height: auto;
        width: auto;
        text-align: center;
    }
    .card1{
        height: auto;
        width: auto;
        background-color: white;
    }
    .card2{
        margin-top: 20px;
        height: auto;
        width: auto;
    }
    .card3{
        margin-top: 20px;
        height: auto;
    }
    .card4{
        margin-top: 20px;
        height: auto;
    }
    .mc-ui-geometry-char{
        font-size: 20px;
        align-content: center;
        color: rgb(85, 154, 244);
        font-weight: bolder;
        letter-spacing:10px;
    }
    .mc-ui-geometry-char1{
        font-size: 20px;
        align-content: center;
        color: rgb(85, 154, 244);
        font-weight: bolder;
        letter-spacing:10px;
    }
    .mc-ui-geometry-char2{
        font-size: 20px;
        align-content: center;
        color: rgb(85, 154, 244);
        font-weight: bolder;
        letter-spacing:10px;
    }
    .mc-ui-geometry-char3{
        font-size: 20px;
        align-content: center;
        color: rgb(85, 154, 244);
        font-weight: bolder;
        letter-spacing:10px;
    }
    .mc-open-dialog-btn{
        float:right;
        height: 42px;
        width: 138px;
    }
    .mc-open-dialog-btn1{
        float:right;
        height: 42px;
        width: 138px;
    }
    .mc-open-dialog-btn2{
        float:right;
        height: 42px;
        width: 138px;
    }
    .mc-open-dialog-btn3{
        float:right;
        height: 42px;
        width: 138px;
    }
    .el-image{
        float:center;
    }
    .el-input{
        height: 22px;
    }
    .editor-data{
        font-weight: bolder;
        width:auto;
        height: auto;
    }
    .account{
        margin-top: 26px;
        font-size: 15px;
        
    }
    .account1{
        margin-top: 50px;
        font-size: 15px;
    }
</style>