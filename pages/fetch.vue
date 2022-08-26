<template>
  <h2>hsfsdg</h2>
</template>

<script>
import axios from "axios";
export default {
//   data() {
//     return {
//       users: [],
//     };
//   },
  async fetch() {
    const users = await axios.get(
      "https://jsonplaceholder.typicode.com/users"
    );
    console.log(users)
  },
};
</script>

<style>
</style>