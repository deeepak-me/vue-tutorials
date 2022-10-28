<template>
  <div class="home">
    <h1>HOME</h1>
    <div v-if="error">{{ error }}</div>
    <div v-if="posts.length">
      <postList :posts="posts" />
    </div>
    <div v-else>Loading...</div>
  </div>
</template>

<script>
import postList from "../components/postList.vue";
import getPosts from "../composables/getPosts";
export default {
  name: "HomeView",
  components: { postList },
  setup() {
    const { posts, error, load } = getPosts();

    load();

    return { posts, error };
  },
};
</script>
