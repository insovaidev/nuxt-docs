<template>
  <div class="container mx-auto mt-8">
    <button class="border-[1px] px-6 py-2 border-blue-400 rounded-xl" @click="showMountaint">Show Laycomponent</button>
    <NuxtLink to="_slug">
      -slug
    </NuxtLink>
    <LazyProductCard v-if="show" />
  </div>
</template>

<script>
export default {
  data() {
    return {
      show: false,
    };
  },
  methods: {
    showMountaint(){
      this.show = true
    }
  }   
};
</script>

<style>
</style>