<template>
  <div class="v-sidebar">
    <div class="top">
      <div class="avatar-wrap">
        <loginable-avatar></loginable-avatar>
      </div>
      <div class="theme-handler"></div>
    </div>
    <div class="list">
      <template v-for="(item, index) in list">
        <template v-if="item.hasOwnProperty('isDivider')">
          <div class="divider van-hairline--bottom" :key="index"></div>
        </template>
        <template v-else>
          <div :class="['list-item', activeIndex === index ? 'active' : '']" :key="index" @click="itemClick(index)">
            <van-icon :name="item.icon" size="20px"></van-icon>
            <div class="title">{{item.title}}</div>
          </div>
        </template>
      </template>
    </div>
  </div>
</template>

<script>
import { Icon } from "vant";
import LoginableAvatar from "@/components/LoginableAvatar";
export default {
  name: "v-sidebar",

  components: {
    [Icon.name]: Icon,
    [LoginableAvatar.name]: LoginableAvatar
  },

  data() {
    return {
      activeIndex: 0,
      list: [
        { icon: "shop", title: "全部", path: "/" },
        { icon: "shop", title: "精华", path: "/" },
        { icon: "shop", title: "分享", path: "/" },
        { icon: "shop", title: "问答", path: "/" },
        { icon: "shop", title: "招聘", path: "/" },
        { isDivider: true },
        { icon: "bell", title: "消息", path: "/" },
        { icon: "setting", title: "设置", path: "/" },
        { icon: "info", title: "关于", path: "/" }
      ]
    };
  },

  props: {},

  methods: {
    itemClick(index) {
      this.activeIndex = index;
      this.$router.push(this.list[index].path);
    }
  }
};
</script>

<style lang="less" scoped>
.v-sidebar {
  width: 315px;
  height: 100vh;
  .top {
    height: 185px;
    background: #dd5a60;
    .avatar-wrap {
      position: absolute;
      left: 15px;
      top: 40px;
    }
  }
  .list {
    padding-top: 6px;
    .list-item {
      display: flex;
      align-items: center;
      height: 46px;
      font-size: 14px;
      .van-icon {
        margin: 0 30px 0 16px;
        color: #7d7d7d;
      }
      &.active {
        background: #efefef;
        color: #88c202;
        .van-icon {
          color: #88c202;
        }
      }
    }
    .divider {
      margin: 6px 0;
    }
  }
}
</style>


