<template>
    <div>
        <van-nav-bar title="购物车" left-text="返回" @click-left="$router.go(-1)" left-arrow="">
        <van-icon name="search" slot="right">
        </van-icon></van-nav-bar>
        <h1>购物车</h1>

        <div v-for="(item,index) in goods" :key="index">{{item.name}}--{{item.num}}</div>
        <div class="col-10"><van-checkbox v-model="checked" checked-color="#ff3300"></van-checkbox></div>
        <div class="col-30">
            <img width="100%" src="img/img.url" alt="">
        </div>
        <div class="col-50"></div>
        <div class="col-10"></div>
        {{item.name}}--{{item.num}}
    </div>
</template>
<script>
// 导入mapstate方法
import {mapState} from 'vuex';
// 插件第一步 导入插件
import { NavBar,Icon, Checkbox} from 'vant';
export default {

    computed:{
        ...mapState(["goods"])
    },
    components:{
        // 02 插件02 注册组件
        [NavBar.name]:NavBar,
        // vant-nav-bar:NavBar
        // es 属性动态设置写法
        [Icon.name]:Icon,
        [checkbox.name]:Checkbox,

    }
}
</script>
<style>
.van-nav-bar van-icon{

}
</style>

