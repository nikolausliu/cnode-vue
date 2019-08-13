<template>
  <div class="article-list">
    <!-- <van-list></van-list> -->
    <article-list-item></article-list-item>
  </div>
</template>

<script>
import { List } from "vant";
import { ArticleListItem } from '@/components';
export default {
  name: "article-list",

  components: {
    [List.name]: List,
    [ArticleListItem.name]: ArticleListItem
  },

  data() {
    return {};
  },

  props: {},

  methods: {}
};
</script>

<style lang="less" scoped>
</style>


