<template>
  <div>
    <h1>記事一覧</h1>
    <p v-if="$fetchState.pending">Fetching posts...</p>
    <ul>
      <li v-for="post in posts" :key="post.id">
        {{post.title}}
      </li>
    </ul>
  </div>
</template>

<script>
  export default {
    data() {
      return {
        posts: [],
      };
    },
    async fetch() {
      const posts = await this.$axios.$get(
        "https://jsonplaceholder.typicode.com/posts/"
      );
      this.posts = posts;
  },
  fetchOnServer: false,
 };
  // export default {
  //   async asyncData({ $axios }) {
  //     const posts = await $axios.$get(
  //       "https://jsonplaceholder.typicode.com/posts/"
  //     );
  //     return { posts };
  //   },
  // };
  </script>
