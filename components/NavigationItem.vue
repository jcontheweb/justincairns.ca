<template>
  <nuxt-link :to="url" class="link font-bold text-2xl relative hover:underline">{{ label }}</nuxt-link>
</template>

<script>
export default {
  props: {
    url: {
      type: String,
      default: "/"
    },
    label: {
      type: String,
      required: true
    }
  }
};
</script>

<style lang="scss">
</style>