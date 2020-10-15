<template>
  <div class="tabbar-item" @click="itemClick">
    <div v-if="!isActive">
      <slot name="item-img"></slot>
    </div>
    <div v-else>
      <slot name="item-img-active"></slot>
    </div>
    <div v-if="isActive" v-bind:class="{active:isActive}" v-bind:style="itemTextColor">
      <slot name="item-text"></slot>
    </div>
    <div v-else v-bind:style="itemTextColor">
      <slot name="item-text"></slot>
    </div>
  </div>
</template>

<script>
  export default {
    name: "TabBarItem",
    props: {
      path: String,
      activeColor: {
        type: String,
        default: '#19fa28'
      }
    },
    data() {
      return {
        // isActive: false
      }
    },
    computed: {
      isActive: {
        get() {
          return this.$route.path.indexOf(this.path) !== -1
        },
        set(val) {

        }
      },
      itemTextColor() {
        return this.isActive ? {color: this.activeColor} : {}
      }
    },
    methods: {
      itemClick() {
        // 如果当前页面不是激活的就跳转，反之不跳转
        if (this.$route.path.indexOf(this.path) === -1) {
          this.$router.replace(this.path)
        }

      }
    }
  }
</script>

<style scoped>
  .tabbar-item {
    flex: 1;
    height: 49px;
    font-size: 14px;
    text-align: center;

  }

  .tabbar-item img {

    width: 24px;
    height: 24px;
    margin-top: 3px;
    vertical-align: middle;
    margin-bottom: 2px;
  }


</style>
