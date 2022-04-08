<template>
    <el-form ref="form" :model="form" label-width="80px">
        <el-card>
            <el-tabs value="first" @tab-click="_tabClick">
                <el-tab-pane name="first" label="选项1">

                    <el-form-item label="特殊资源">
                        <el-radio-group>
                        <el-radio label="线上品牌商赞助"></el-radio>
                        <el-radio label="线下场地免费"></el-radio>
                        </el-radio-group>
                    </el-form-item>

                    <el-form-item label="活动名称">
                        <el-input></el-input>
                    </el-form-item>

                    <el-form-item label="活动名称">
                        <el-input></el-input>
                        <el-input></el-input>
                    </el-form-item>

                    <el-form-item label="活动名称">
                        <el-input></el-input>
                        <el-input></el-input>
                    </el-form-item>

                    <el-button type="primary" @click="onSubmit">立即创建</el-button>
                        <el-link>文字链接</el-link>
                </el-tab-pane>
                <el-tab-pane name="second" label="选项2">

                    <el-form-item label="特殊资源">
                        <el-radio-group>
                            <el-radio label="线上品牌商赞助"></el-radio>
                            <el-radio label="线下场地免费"></el-radio>
                            <el-radio label="线下场地免费"></el-radio>
                            <el-radio label="线下场地免费"></el-radio>
                        </el-radio-group>
                    </el-form-item>

                    <el-form-item label="活动名称">
                        <el-input></el-input>
                        <el-form-item label="X">
                        <el-input></el-input>
                        <el-form-item label="活动名称"> 
                        </el-form-item>
                        </el-form-item>
                    </el-form-item>
                    <el-form-item label="活动名称">
                        <el-input></el-input>
                    </el-form-item>

                    <el-button type="primary" @click="onSubmit">立即创建</el-button>
                    <el-link>文字链接</el-link>
                </el-tab-pane>
                <el-tab-pane name="third" label="选项3">
                </el-tab-pane>

            </el-tabs>
        </el-card>
    </el-form>
</template>

<style scoped>
.el-tab-pane{
    width: 800px;
    vertical-align: center;
}
.el-tag{
    font-size: 16px;
    max-height: 578px;
    background: none;
}
.el-card{
    margin-left: 37px;
    margin-right:37px;
    width: 840px;
    height: 466px;
    margin-bottom: 20px;
}
</style>