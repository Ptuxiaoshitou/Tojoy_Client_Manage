<template>
  <div class = "home">
    <el-container style="height : 100%">
      <el-header>
        <common-aside></common-aside>
      </el-header>
      <el-container>
        <el-container>
          <el-main>
              <!-- 广告轮播 -->
              <main-ad></main-ad>
              <!-- 在线计价 -->
                <online-com>
              <!-- 在线下单 -->
                </online-com>
                <el-container>
                    <online-container></online-container>
                    <online-login></online-login>
                </el-container>
                <el-container>
                    <custom-list></custom-list>
                </el-container>
                <el-container>
                  <custom-show></custom-show>
                </el-container>
                <el-container>
                  </el-container>
          </el-main>
          <el-footer>Footer</el-footer>
        </el-container>
      </el-container>
    </el-container>
  </div>
</template>
<script>


import CommonAside from '../src/components/CommonAside.vue'
import MainAd from '../src/components/MainAd.vue'
import OnlineCom from '../src/components/OnlineCom.vue'
import OnlineContainer from '../src/components/OnlineContainer.vue'
import OnlineLogin from '../src/components/OnlineLogin.vue'
import CustomList from '../src/components/CustomList.vue'
import CustomShow from '../src/components/CustomShow.vue'

export default{
    name:'Home',
    components:{
        CommonAside,
        MainAd,
        OnlineCom,
        OnlineContainer,
        OnlineLogin,
        CustomList,
        CustomShow
    },
    data(){
        return {}
    }
} 
</script>
<style lang="less" scoped>
.el-header{
    background-color: rgb(92, 195, 243);
}
.el-main{
    padding-top: 0;
}
</style>