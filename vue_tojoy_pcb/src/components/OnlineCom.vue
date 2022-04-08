<template>
  <el-row :gutter="20">
      <el-container>
        <!-- 替换成公司资讯 -->
          <el-col :span="12"><div class="grid-content bg-purple">在线计价</div>
          </el-col>
          <!-- 用户登录 现主要完成这个登录界面-->
            <el-col :span="12"><div class="grid-content bg-purple">用户登录</div> 
            </el-col>
      </el-container>
  </el-row>
</template>



<style scoped>
  .el-row {
    margin-bottom: 20px;
    /* &:last-child {
      margin-bottom: 0;
    } */
  }
  .el-col {
    border-radius: 4px;
    font-size: 19px;
    text-align:center;
    line-height: 2.6 ;
    font-family: "Helvetica Neue",Helvetica,"PingFang SC","Hiragino Sans GB","Microsoft YaHei","微软雅黑",Arial,sans-serif;
    color: white;
  }
  .bg-purple-dark {
    background: #73aaf7;
  }
  .bg-purple {
    background: #e41313;
  }
  .bg-purple-light {
    background: #e5e9f2;
  }
  .grid-content {
    border-radius: 8px;
    min-height: 48px;

  }
  .row-bg {
    padding: 10px 0;
    background-color: #f9fafc;
  }
  .grid-content bg-purple{
      font-size: 15px;
  }
</style>