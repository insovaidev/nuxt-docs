<template>
  <div class="container mx-auto mt-8">
    <ProductCard :product="product" />
    <pre>{{ post }}</pre>
  </div>
</template>

<script>
import ProductCard from ".././components/ProductCard";
export default {
  components: {
    ProductCard,
  },
  data() {
    return {
      product: {
        title: "gjdfgjgjd",
        image: "dfgjsjdg",
        description: "gjdfgjgjd",
        continent: "dfgjsjdg",
      },
    };
  },
  async asyncData({ $axios }) {
    try {
      const post = await $axios.$get(`https://api.nuxtjs.dev/posts/1`);
      console.log(post);
      if (Object.keys(post).length > 0) {
        this.product.title = post.title;
        
      }
    } catch (error) {

      console.log(error);
    }
    // console.log("================");
    // console.log(this.product.title);

    // return { post };
  },
};
</script>

<style>
</style>