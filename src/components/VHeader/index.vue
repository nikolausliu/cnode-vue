<template>
  <div class="v-header">
    <van-icon name="wap-nav" class="icon"></van-icon>
    <span>{{title}}</span>
  </div>
</template>

<script>
import {Icon} from 'vant';
export default {
  name: 'v-header',

  components: {
    [Icon.name]: Icon
  },

  data() {
    return {
      
    };
  },

  props: {
    title: {
      type: String,
      default: 'CNode社区'
    }
  }
}
</script>

<style lang="less" scoped>
  .v-header {
    display: flex;
    align-items: center;
    height: 52px;
    background: rgb(51, 51, 51);
    color: #fff;
    .icon {
      margin: 0 30px 0 15px;
      font-size: 20px;
    }
  }
</style>


