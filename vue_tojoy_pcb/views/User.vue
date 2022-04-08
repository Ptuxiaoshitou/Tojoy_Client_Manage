<template>
    <div class='background'>
        <el-container style = "height:100%">
         <el-aside width="auto">
             <user-aside>
             </user-aside>
         </el-aside>
            <el-container>
                <el-header>
                    <user-header>                        
                    </user-header>
                    <img :src="src" class="image"></img>   
                        <input class='search'placeholder="请输入搜索内容"> </input>
                </el-header>
                <el-main>
                    <user-pageone></user-pageone>
                </el-main>
            </el-container>
        </el-container>
    </div>
</template>

<script>
import UserAside from '../src/components/UserAside.vue'
import UserHeader from '../src/components/UserHeader.vue'
import UserPageone from '../src/components/UserPageone.vue'

export default{
    
    name:'User',
     components:{
        UserAside,
        UserHeader,
        UserPageone
    },
    data(){
        return {
            // showDialog: false,
            // showDialog1: false,
            // checked_qq: false,
            // checked_tel: false,
            // checked_telnum: false,
            // checked_mail: false,
            // input: '',
            // input1: '',
            // search:'',
            src:require("@/assets/images/20161024092315.png"),  //require获取动态路径

        };
    },
}
</script>

<style lang="less" scoped>
    .el-header{
        background-color: #DDDDDC;
        text-align: center;
    }
    .el-main{
        padding :0;
    }
    .image{
        height: 28px;
        // float:right;
        // margin-right: 800px;
        margin-top: 15px;
        
    }
    // .el-card{
    //     height: 1000px;
    //     width: auto;
    //     text-align: center;
    // }
    // .card1{
    //     height: 256px;
    //     width: auto;
    //     background-color: white;
    // }
    // .card2{
    //     margin-top: 20px;
    // }
    // .mc-ui-geometry-char{
    //     font-size: 20px;
    //     align-content: center;
    //     color: rgb(85, 154, 244);
    //     font-weight: bolder;
    //     letter-spacing:10px;
    // }
    // .mc-ui-geometry-char1{
    //     font-size: 20px;
    //     align-content: center;
    //     color: rgb(85, 154, 244);
    //     font-weight: bolder;
    //     letter-spacing:10px;
    // }
    // .mc-open-dialog-btn{
    //     float:right;
    //     height: 42px;
    //     width: 138px;
    // }
    // .mc-open-dialog-btn1{
    //     float:right;
    //     height: 42px;
    //     width: 138px;
    // }
    // .el-image{
    //     float:center;
    // }
    .search{
        float: right;
        margin-top: 15px;
        border-radius:10px;
        height: 30px;
        border-block-color: white;
    }
    // .editor-data{
    //     font-weight: bolder;
    // }
</style>