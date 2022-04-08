<template>
<el-menu default-active="1-4-1" class="el-menu-vertical-demo" @open="handleOpen" @close="handleClose" :collapse="isCollapse">
    <!-- 渲染   v-for ="item in noChildren" : index="item.path" key="item.path" "'el-icon-' + item.icon"-->
  <el-submenu index="1">
    <template slot="title">
      <i class='el-icon-menu'></i>
      <!-- {item.label} -->
      <span slot="title">客户资料</span> 
    </template>
    <el-menu-item-group>
      <el-menu-item index="1-1">查看客户资料</el-menu-item>
      <el-menu-item index="1-2">修改登录密码</el-menu-item>
      <el-menu-item index="1-3">修改绑定手机</el-menu-item>
      <el-menu-item index="1-4">修改登录密码</el-menu-item>
      <el-menu-item index="1-5">消息通知设置</el-menu-item>
      <el-menu-item index="1-6">微信账号绑定</el-menu-item>
    </el-menu-item-group>
  </el-submenu>
    <el-submenu index="2">
        <template slot="title">
            <i class="el-icon-menu"></i>
            <span slot="title">预付款</span>
        </template>
    <el-menu-item-group>
      <el-menu-item index="2-1">使用说明</el-menu-item>
      <el-menu-item index="2-2">线下充值</el-menu-item>
      <el-menu-item index="2-3">现金帐户管理</el-menu-item>
      <el-menu-item index="2-4">充值记录</el-menu-item>
      <el-menu-item index="2-5">交易明细</el-menu-item>
      <el-menu-item index="2-6">提现记录</el-menu-item>
      <el-menu-item index="2-7">充值记录</el-menu-item>
      <el-menu-item index="2-8">支付密码设置/修改</el-menu-item>
      <el-menu-item index="2-9">补款记录列表</el-menu-item>
    </el-menu-item-group>
  </el-submenu>
  <el-submenu index="3">
        <template slot="title">
            <i class="el-icon-document"></i>
            <span slot="title">产品列表</span>
        </template>
    <el-menu-item-group>
      <el-menu-item index="3-1">使用说明</el-menu-item>
    </el-menu-item-group>
  </el-submenu>
    <el-submenu index="4">
        <template slot="title">
            <i class="el-icon-document"></i>
            <span slot="title">订单管理</span>
        </template>
    <el-menu-item-group>
      <el-menu-item index="4-1">使用说明</el-menu-item>
      <el-menu-item index="2-2">线下充值</el-menu-item>
      <el-menu-item index="2-3">现金帐户管理</el-menu-item>
      <el-menu-item index="2-4">充值记录</el-menu-item>
      <el-menu-item index="2-5">交易明细</el-menu-item>
      <el-menu-item index="2-6">提现记录</el-menu-item>
      <el-menu-item index="2-7">充值记录</el-menu-item>
      <el-menu-item index="2-8">支付密码设置/修改</el-menu-item>
      <el-menu-item index="2-9">补款记录列表</el-menu-item>
    </el-menu-item-group>
  </el-submenu>
    <el-submenu index="5">
        <template slot="title">
            <i class="el-icon-setting"></i>
            <span slot="title">售后服务</span>
        </template>
    <el-menu-item-group>
      <el-menu-item index="5-1">pcb品质投诉</el-menu-item>
      <el-menu-item index="5-2">钢网品质投诉</el-menu-item>
      <el-menu-item index="5-3">SMT品质投诉</el-menu-item>
      <el-menu-item index="5-4">投诉工作人员</el-menu-item>
      <el-menu-item index="5-5">QC缺数处理</el-menu-item>
      <el-menu-item index="5-6">售后备注</el-menu-item>
      <el-menu-item index="5-7">退款记录</el-menu-item>
    </el-menu-item-group>
  </el-submenu>
</el-menu>
</template>
<style>
  .el-menu-vertical-demo:not(.el-menu--collapse) {
    width: 200px;
    min-height: 400px;
  }
</style>

<script>
  export default {
    data() {
      return {
        isCollapse: false,
        menu :[
            {
                path:'/',
                name:'home',
                label:'客户资料',
                icon:'s-home',
                url:'Home/Home'
            },
            {
                path:'/mall',
                name:'mall',
                label:'商品管理',
                icon:'video-play',
                url:'MallManage/MallManage'
            },
            {
                path:'/user',
                name:'user',
                label:'用户管理',
                icon:'user',
                url:'UserManage/UserManage'
            },
            {
                label:'其它',
                icon:'location',
                children:[
                    {
                    path:'/page1',
                    name:'page1',
                    label:'页面1',
                    icon:'setting',
                    url:'Other/PageOne'
                    },
                                        {
                    path:'/page2',
                    name:'page2',
                    label:'页面2',
                    icon:'setting',
                    url:'Other/PageTwo'
                    },
                ]
            }
        ]
      };
    },
    methods: {
      handleOpen(key, keyPath) {
        console.log(key, keyPath);
      },
      handleClose(key, keyPath) {
        console.log(key, keyPath);
      }
    },
    // 处理数据 menu
    computed:{
        // 没有子项目
        noChildren(){
            this.menu.filter(item => !item.children)
        },
        // 有子项目
        hasChiledren(){
            this.menu.filter(item => item.children)
        }
    }
  }
</script>