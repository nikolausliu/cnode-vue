<template>
  <div class="v-header">
    <van-icon
      v-if="leftIconName"
      :name="leftIconName"
      class="left-icon"
      @click="leftIconClickHandle"
    ></van-icon>
    <span v-if="title" class="title" @click="titleClickHandle">{{title}}</span>
    <van-icon
      v-if="rightIconName"
      :name="rightIconName"
      class="right-icon"
      @click="rightIconClickHandle"
    ></van-icon>
  </div>
</template>

<script>
import { Icon } from "vant";

export default {
  name: "v-header",

  components: {
    [Icon.name]: Icon
  },

  data() {
    return {};
  },

  props: {
    leftIconName: {
      type: String,
      default: ""
    },
    rightIconName: {
      type: String,
      default: ""
    },
    title: {
      type: String,
      default: ""
    }
  },

  methods: {
    leftIconClickHandle() {
      this.$emit("click-left");
    },
    titleClickHandle() {
      this.$emit("click-title");
    },
    rightIconClickHandle() {
      this.$emit("click-right");
    }
  }
};
</script>

<style lang="less" scoped>
@height: 52px;
.v-header {
  position: relative;
  height: @height;
  padding: 0 15px;
  background: rgb(51, 51, 51);
  color: #fff;
  .left-icon {
    float: left;
    margin-right: 30px;
    line-height: @height;
    font-size: 20px;
  }
  .title {
    float: left;
    line-height: @height;
  }
  .right-icon {
    float: right;
    line-height: @height;
  }
}
</style>


