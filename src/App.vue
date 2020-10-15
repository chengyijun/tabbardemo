<template>
  <div id="app">
    <router-view></router-view>
    <tab-bar>
      <tab-bar-item path="/home">
        <img slot="item-img" src="./assets/img/主页.svg" alt="">
        <img slot="item-img-active" src="./assets/img/主页a.svg" alt="">
        <div slot="item-text">首页</div>
      </tab-bar-item>
      <tab-bar-item path="/category">
        <img slot="item-img" src="./assets/img/分类.svg" alt="">
        <img slot="item-img-active" src="./assets/img/分类a.svg" alt="">
        <div slot="item-text">分类</div>
      </tab-bar-item>
      <tab-bar-item path="/shopcart">
        <img slot="item-img" src="./assets/img/购物车.svg" alt="">
        <img slot="item-img-active" src="./assets/img/购物车a.svg" alt="">
        <div slot="item-text">购物车</div>
      </tab-bar-item>
      <tab-bar-item path="profile">
        <img slot="item-img" src="./assets/img/我的.svg" alt="">
        <img slot="item-img-active" src="./assets/img/我的a.svg" alt="">
        <div slot="item-text">我的</div>
      </tab-bar-item>
    </tab-bar>
  </div>
</template>

<script>
  import TabBar from "./components/TabBar";
  import TabBarItem from "./components/TabBarItem";

  export default {
    name: 'App',
    components: {
      TabBar,
      TabBarItem
    }

  }
</script>

<style>
  @import "assets/css/base.css";


</style>
