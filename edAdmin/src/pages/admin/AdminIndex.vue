<template>
  <div class="homePage adminIndex">
    <el-row style="height: 100%;">
        <el-col :span="4"  style="min-height: 100%; background-color: #324057;">
            <el-menu :default-active="defaultActive" style="min-height: 100%;" theme="dark" router>
                <!-- 首页 -->
                <el-menu-item index="admin"><i class="el-icon-menu"></i>首页</el-menu-item>
                <!-- <el-menu-item index="TimeMachine"><i class="el-icon-s-marketing"></i>时光机</el-menu-item> -->
                <el-menu-item index="notFinished"><i class="el-icon-s-marketing"></i>时光机</el-menu-item>
                <!-- 单词 -->
                <el-submenu index="2">
                    <template slot="title"><i class="el-icon-s-order"></i>单词管理</template>
                    <el-menu-item index="wordInput">单词输入</el-menu-item>
                    <el-menu-item index="wordAdmin" disabled>单词查询</el-menu-item>
                    <el-menu-item index="wordAdmin" disabled>单词分类</el-menu-item>
                </el-submenu>
                <!-- 语法 -->
                <el-submenu index="3">
                    <template slot="title"><i class="el-icon-s-promotion"></i>语法文章</template>
                    <el-menu-item index="grammarAdmin" disabled>语法输入</el-menu-item>
                    <el-menu-item index="grammarAdmin" disabled>文章输入</el-menu-item>
                </el-submenu>
                <el-submenu index="4">
                    <template slot="title"><i class="el-icon-s-claim"></i>积分系统</template>
                    <el-menu-item index="integralSystem" disabled>账号等级</el-menu-item>
                    <el-menu-item index="integralSystem" disabled>积分管理</el-menu-item>
                </el-submenu>
                <!-- 附录 -->
                <el-submenu index="5">
                    <template slot="title" index="appendix"><i class="el-icon-star-on"></i>附录</template>
                    <el-menu-item index="appendix" disabled>地图</el-menu-item>
                    <el-menu-item index="appendix" disabled>神话</el-menu-item>
                </el-submenu>
                <!-- 设置 -->
                <el-submenu index="6">
                    <template slot="title"><i class="el-icon-s-tools"></i>设置</template>
                    <el-menu-item index="settingAdmin">管理员设置</el-menu-item>
                    <el-menu-item index="setting" disabled>主题设置</el-menu-item>
                </el-submenu>
            </el-menu>
        </el-col>
        <el-col :span="20" style="height: 100%;overflow: auto;">
            <keep-alive>
                <router-view></router-view>
            </keep-alive>
        </el-col>
    </el-row>
  </div>
</template>
<script>
export default {
  computed: {
			defaultActive (){
				return this.$route.path.replace('/', '');
			}
		}
};
</script>
<style scoped>
.homePage {
    width: 100%;
    height: 100%;
}
</style>
