<template>
  <div>

    <!-- <pre>{{ post }}</pre> -->
    <!-- <h1>{{ post.title }}</h1>
    <p>{{ post.description }}</p> -->
  </div>
</template>

<script>
import axios from "axios";
export default {
  
  // -----------query
  // async asyncData(req) {
  //   const id = req.route.query.id 
  //   const post = await axios.get(`https://api.nuxtjs.dev/posts/${id}`);
  //   console.log(post)
  //   return { post };
  // },

  // ----------params
  async asyncData({ $axios }) {
    const post = await $axios.$get(`https://jsonplaceholder.typicode.com/users`);
    console.log(post)


  },
};
</script>

<style>
</style>