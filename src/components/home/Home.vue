<template>
    <el-container id="container">
        <el-aside width="300px">
            <el-container id="top">
                <img style="width:25px;height:25px;margin:auto;margin-right:0;" src="~@/assets/sociallogo.png"/>
 
                <div style="margin:auto;margin-left:10px;color:#ffffff;font-size:2rem">
                    SRMS
                </div>
            </el-container>
            <el-menu
            :default-active="$route.path"
            style="height:100%"
            background-color="#545c64"
            text-color="#fff"
            active-text-color="#ffd04b"
            @select="selectItem">
            <el-submenu index="1">
                <template #title>
                <i class="el-icon-s-order"></i>
                <span>Friends</span>
                </template>
                <el-menu-item index="/home/order/0">Normal Friends</el-menu-item>
                <el-menu-item index="/home/order/1">Close Friends</el-menu-item>
            </el-submenu>
            <el-submenu index="2">
                <template #title>
                <i class="el-icon-s-shop"></i>
                <span>Professional</span>
                </template>
                <el-menu-item index="/home/goods/0">Service Provider</el-menu-item>
                <el-menu-item index="/home/goods/1">Investors/Boss</el-menu-item>
                <el-menu-item index="/home/goods/2">Colleagues</el-menu-item>
      
            </el-submenu>

            <el-submenu index="3">
            <template #title>
                <i class="el-icon-s-shop"></i>
                <span>Category</span>
                </template>
                <el-menu-item index="/home/category">Category</el-menu-item>
             
            </el-submenu>
            <!-- <el-submenu index="3">
                <template #title>
                <i class="el-icon-s-custom"></i>
                <span>店长管理</span>
                </template>
                <el-menu-item index="/home/ownerlist">店长列表</el-menu-item>
                <el-menu-item index="/home/ownerreq">店长申请审批列表</el-menu-item>
                <el-menu-item index="/home/ownerorder">店长订单</el-menu-item>
            </el-submenu> -->
            <el-submenu index="4">
                <template #title>
                <i class="el-icon-s-ticket"></i>
                <span>Data Management</span>
                </template>
                <el-menu-item index="/home/tradeinfo">Data Summary</el-menu-item>
                <el-menu-item index="/home/tradelist">reconciliation</el-menu-item>
            </el-submenu>
            <el-submenu index="5">
                <template #title>
                <i class="el-icon-s-tools"></i>
                <span>SRMS</span>
                </template>
                <el-menu-item index="/home/data">Data</el-menu-item>
            </el-submenu>
            </el-menu>
        </el-aside>
        <el-main style="padding:0">
            <!-- add a header  -->
            <el-header style="margin:0;padding:0;" height="80px">
                <el-container style="background-color:blanchedalmond;margin:0;padding:0;height:80px">
                    <div style="margin: auto;margin-left:100px"><h1>Thanks for Using Social Relationship Management System！</h1></div>
                    <div style="margin: auto;margin-right:50px"><el-button type="primary" @click="logout">Logout</el-button></div>
                </el-container>
            </el-header>
            <!-- import route view -->
            <router-view></router-view>
        </el-main>
    </el-container>
</template>

<script>
import Storage from '../../tools/Storage'
export default {
    name:"Login",
    methods: {
        logout() {
            Storage.commit('clearUserInfo');
            this.$router.push({name:'login'})
        },
        selectItem(index) {
            this.$router.push(index)
        }
    },
}
</script>

<style scoped>
#container {
    height: 100%;
    width:100%;
    position: absolute;
}
#top {
    background-color:#545c64;
    margin-right:1px;
    text-align: center;
    height: 60px;
}

</style>