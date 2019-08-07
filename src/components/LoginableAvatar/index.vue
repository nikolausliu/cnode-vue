<template>
  <div class="loginable-avatar">
    <template v-if="islogin">
      <div class="islogin">
        <div class="avatar">
          <img :src="defaultAvatar" alt />
        </div>
        <div class="info">
          <div class="username">nikolausliu</div>
          <div class="point">积分：0</div>
          <div class="logout">注销</div>
        </div>
      </div>
    </template>
    <template v-else>
      <div class="notlogin">
        <div class="avatar" @click="clickAvatar">
          <img :src="defaultAvatar" alt />
        </div>
        <div class="info">点击头像登录</div>
      </div>
    </template>
  </div>
</template>

<script>
import { Icon } from "vant";
export default {
  name: "loginable-avatar",

  components: {
    [Icon.name]: Icon
  },

  data() {
    return {
      defaultAvatar: require("./avatar.png"),
      avatar: require("./avatar.png")
    };
  },

  props: {
    islogin: {
      type: Boolean,
      default: true
    }
  },

  methods: {
    login() {},
    logout() {}
  }
};
</script>

<style lang="less" scoped>
.loginable-avatar {
  .avatar {
    position: relative;
    width: 70px;
    height: 70px;
    border-radius: 50%;
    overflow: hidden;
    background: #fff;
    img {
      display: block;
      width: 100%;
      height: 100%;
    }
  }
  .info {
    position: relative;
    margin-top: 18px;
    width: 265px;
  }
  .islogin {
    .info {
      font-size: 14px;
      line-height: 16px;
      .username {
        color: #fff;
      }
      .point {
        margin-top: 8px;
        color: #f1f1f1;
      }
      .logout {
        display: inline-block;
        position: absolute;
        right: 0;
        bottom: 0;
        color: #f1f1f1;
      }
    }
  }
  .notlogin {
    .info {
      color: #fff;
      font-size: 14px;
      line-height: 16px;
    }
  }
}
</style>


