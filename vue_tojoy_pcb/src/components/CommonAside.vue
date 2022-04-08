<template>
  <el-menu :default-active="activeIndex" class="el-menu-demo" mode="horizontal" @select="handleSelect">
      <el-menu-item index="1">PCB首页</el-menu-item>
    <el-submenu index="2">
    <template slot="title">在线计价</template>
      <el-menu-item index="2-1">在线计价</el-menu-item>
      <el-menu-item index="2-2">立即下单</el-menu-item>
      <el-menu-item index="2-3">阻抗神器</el-menu-item></el-submenu>
    <el-submenu index="3">
    <template slot="title">产品展示</template>
      <el-menu-item index="3-1">PCB打样/小批量</el-menu-item>
      <el-menu-item index="3-2">SMT贴片</el-menu-item>
      <el-menu-item index="3-3">激光钢网</el-menu-item></el-submenu>
      <el-menu-item index="5" >工艺参数</el-menu-item>
    <el-submenu index="4">
    <template slot="title">SMT打样</template>
      <el-menu-item index="4-1">SMT打样介绍</el-menu-item>
      <el-menu-item index="4-2">器件清单</el-menu-item>
      <el-menu-item index="4-3">立即下单</el-menu-item>
    </el-submenu>
    <el-submenu index="5">
    <template slot="title">关于我们</template>
      <el-menu-item index="5-1">联系我们</el-menu-item>
      <el-menu-item index="5-2"> <a href="http://www.to-joy.com" target="_blank">公司简介</a></el-menu-item>
      <el-menu-item index="5-3">发展历史</el-menu-item>
      <el-menu-item index="5-4">服务发展</el-menu-item>
      <el-menu-item index="5-5">付款方式</el-menu-item>
    </el-submenu>
    <el-menu-item index="6">第三方服务平台</el-menu-item>
    <el-menu-item index="7"><a href="http://www.to-joy.com" target="_blank">订单管理</a></el-menu-item>
  </el-menu>
</template>

<script scoped>
  export default {
    data() {
      return {
        activeIndex: '1',
        activeIndex2: '1',
        // 用于后面做动态组件
        menu:[
          // 首页
          {
            path:'/',
            name:'home',
            label:'首页',
            icon:'',
            url:'Home/Home'
          },
          // 工艺参数
          {
            path:'/',
            name:'home',
            label:'工艺参数',
            icon:'',
            url:'Home/Home'
          },
          {
            path:'/',
            name:'home',
            label:'工艺参数',
            icon:'',
            url:'Home/Home'
          },
          {
            path:'/',
            name:'home',
            label:'第三方服务平台',
            icon:'',
            url:'Home/Home'
          }, 
         {
           label:'在线下单',
           icon:'',
           children : [
             {
               path :'/page1',
               name : 'page1',
               label : '页面1',
               icon : '',
               url : 'Other/PageOne'
             },
                          {
               path :'/page1',
               name : 'page1',
               label : '页面1',
               icon : '',
               url : 'Other/PageOne'
             },
                          {
               path :'/page1',
               name : 'page1',
               label : '页面1',
               icon : '',
               url : 'Other/PageOne'
             }
           ]
         }
        ]
      };
    },
    methods: {
      handleSelect(key, keyPath) {
        console.log(key, keyPath);
      }
    },
    // 处理数据 分成两组，一组没有子菜单，一组有子菜单
    computed:{
      noChildren(){
        // 将拿到的数据源进行过滤 过滤函数
        // 没有子菜单的
        this.menu.filter(item => !item.children)
      },
      hasChildren(){
        // 有子菜单的
        this.menu.filter(item => item.children)
      }
  }
}
</script>

<style>

</style>
