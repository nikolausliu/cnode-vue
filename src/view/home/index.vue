<template>
  <div class="home">
    <v-header
      left-icon-name="wap-nav"
      :title="title"
      @click-left="openSidebar"
      @click-title="backTop"
    ></v-header>

    <van-popup v-model="sidebarVisible" position="left">
      <v-sidebar></v-sidebar>
    </van-popup>

    <article-list></article-list>
  </div>
</template>

<script>
import { Popup } from "vant";
import { VHeader, VSidebar, ArticleList } from "@/components";
export default {
  components: {
    [Popup.name]: Popup,
    [VHeader.name]: VHeader,
    [VSidebar.name]: VSidebar,
    [ArticleList.name]: ArticleList,
  },

  data() {
    return {
      title: "CNode社区",
      sidebarVisible: false
    };
  },

  created() {},

  methods: {
    openSidebar() {
      this.sidebarVisible = true;
    },
    backTop() {}
  }
};
</script>

<style lang="less">
</style>
