<template>
  <div class="container mx-auto">
    <div class="relative py-16 bg-white overflow-hidden">
      <NuxtLink to="/products"> &larr; Products</NuxtLink>
      <div class="relative px-4 sm:px-6 lg:px-8">
        <div class="text-lg max-w-pros mx-auto mb-6">
          <p
            class="
              text-base text-center
              leading-6
              text-indigo-600
              font-semibold
              tracking-wide
              u
            "
          >
            {{ mountain.continent }}
          </p>
          <h1
            class="
              mt-2
              mb-8
              text-3xl text-center
              leading-8
              font-extrabold
              tracking-tight
              text-gray-900
              sm:text-4xl sm:leading-10
            "
          >
            {{ mountain.title }}
          </h1>
        </div>
        <figure>
          <img
            class="w-auto rounded-lg mx-auto"
            :src="mountain.image"
            alt=""
            width="1310"
            height="873"
          />
          <figcaption class="text-center">{{ mountain.title }}</figcaption>
        </figure>
        <div class="prose prose-lg text-gray-500 mx-auto">
          <ul>
            <li><span class="font-bold">Height</span> {{ mountain.height }}</li>
            <li><span class="font-bold">Country:</span><span v-for="country in mountain.countries" :key="country">{{country}}</span></li>
          </ul>
          <p>{{ mountain.description }}</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>

export default {
  async asyncData({ params, $axios }) {
    const mountain = await $axios.$get(
      `https://api.nuxtjs.dev/mountains/${params.slug}`
    );
    return { mountain };
  },
};
</script>

<style scoped>
svg {
  width: 20px;
  height: 20px;
  display: inline-block;
}
</style>