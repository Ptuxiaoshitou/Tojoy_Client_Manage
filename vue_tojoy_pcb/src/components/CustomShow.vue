<template>
    <div class="index">
        <!-- 跑马灯  -->
        <div>   
            <el-carousel :interval="4000" type="card" height="400px">
                <el-carousel-item v-for="item in imgList" :key="item.id">
                     <img :src="item.idView" class="image">
                </el-carousel-item>
            </el-carousel>
        </div>
    </div>
</template>


<script>
export default {
    name: 'index',
    data(){
        return {
            imgList: [ 
                // {id:0,idView:require("@/assets/images/pcb1.png")},  //require获取动态路径
                // {id:1,idView:require("@/assets/images/pcb1.png")},
                // {id:2,idView:require("@/assets/images/pcb1.png")},
                // {id:3,idView:require("@/assets/images/pcb1.png")},
                // {id:4,idView:require("@/assets/images/pcb1.png")},     
                // {id:5,idView:require("@/assets/images/pcb1.png")},  
            ]
        };
        },
    methods: { 
    }
}
</script>
<style scoped   >
  .index{
    width: 100%;
    text-align: center;
    background-color: aquamarine;
  }
  .el-carousel__item h3 {
    color: #475669;
    font-size: 14px;
    opacity: 0.75;
    line-height: 200px;
    margin: 0;
  }
  
</style>