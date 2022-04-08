<template>
    <el-link class = "link1">您的位置：客户资料 </el-link>
</template>


<script>
export default {
    data(){
        return {
            src:require("@/assets/images/20161024092315.png"),  //require获取动态路径
        };
    }
}
</script>
<style scoped>
.link1{
    float: left;
    position: relative;
    margin-top: 20px;

}
</style>