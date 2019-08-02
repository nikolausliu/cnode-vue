<template>
  <div class="v-sidebar">
    <div class="top">
      <div class="avatar-wrap">
        <div class="avatar"></div>
        <span>点击头像登录</span>
      </div>
      <div class="theme-handler"></div>
    </div>
    <div class="v-sidebar-item"></div>
  </div>
</template>

<script>
import {Icon} from 'vant';
export default {
  name: 'v-sidebar',

  components: {
    [Icon.name]: Icon
  },

  data() {
    return {
      
    };
  },

  props: {
  }
}
</script>

<style lang="less" scoped>
  .v-sidebar {
    width: 500px;
    .top {
      height: 185px;
    }
  }
</style>


