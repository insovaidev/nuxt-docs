<template>
  <div>
<div class="flex items-center space-x-2 mb-4">
  <pre>{{mountains}}</pre>
      <button  @click="$fetch">Refresh</button>
      <div v-show="$fetchState.pending" class="loading"></div>
    </div>

    <p v-if="$fetchState.error">An error occured :(</p>
    <div
      class="md:flex mb-4 flex  text-left"
      v-for="mountain in mountains"
      :key="mountain.title"
    >
      <div class="md:flex-shrink-0">
        <img class="rounded-lg md:w-56" :src="mountain.image" alt="" />
      </div>
      <div class="mt-4 md:mt-0 md:ml-6">
        <div class="uppercase tracking-wide text-sm text-indigo-600 font-bold">
          {{ mountain.continent }}
        </div>
        <NuxtLink
          :to="mountain.slug"
          class="
            block
            mt-1
            text-xl
            landing-tight
            font-semibold
            text-gray-900
            hover:underline
          "
          >{{ mountain.title }}</NuxtLink
        >

        <p class="mt-2 text-gray-600">{{ mountain.description }}</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  async fetch() {
    this.mountains = await fetch("https://api.nuxtjs.dev/mountains").then(
      (res) => res.json()
    );
  },
  data() {
    return {
      mountains: [],
    };
  }
};
</script>

<style>
.loading {
  /* display: inline-block; */
  width: 1.5rem;
  height: 1.5rem;
  border: 4px solid rgba(9, 133, 81, 0.705);
  border-radius: 50%;
  border-top-color: #158876;
  animation: spin 1s ease-in-out infinite;
}
@keyframes spin {
  to {
    -webkit-transform: rotate(360deg);
  }
}
</style>