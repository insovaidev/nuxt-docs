<template>
  <div class="md:flex">
    <div class="md:flex-shrink-0">
      <img class="rounded-lg md:w-56" :src="product.image" alt="" />
    </div>
    <div class="mt-4 md:mt-0 md:ml-6">
      <div class="uppercase tracking-wide text-sm text-indigo-600 font-bold">
        {{ product.continent }}
      </div>
      <a
        href="#"
        class="
          block
          mt-1
          text-xl
          landing-tight
          font-semibold
          text-gray-900
          hover:underline
        "
      >
        {{}}
      </a>
      <p class="mt-2 text-gray-600">sjgknsagjaskg</p> 
    </div>
  </div>
</template>

<script>
export default {
  props: {
    product: {
      type: Object,
      default: () => {},
    },
  },
};
</script>

<style>
</style>