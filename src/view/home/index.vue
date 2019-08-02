<template>
  <div class="home">
    <v-header left-icon-name="wap-nav" right-icon-name="search" :title="title"></v-header>
  </div>
</template>

<script>
import { VHeader } from "@/components";
export default {
  components: {
    [VHeader.name]: VHeader
  },

  data() {
    return {
      title: 'CNode社区'
    };
  },

  created() {},

  methods: {}
};
</script>

<style lang="less">
</style>
