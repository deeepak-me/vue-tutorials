<template>
  <div class="postList">
    <div v-for="post in posts" :key="post.id">
      <singlePost :post="post" />
    </div>
  </div>
</template>

<script>
import singlePost from "./singlePost.vue";
export default {
  props: ["posts"],
  components: { singlePost },
  setup(props) {},
};
</script>

<style></style>
