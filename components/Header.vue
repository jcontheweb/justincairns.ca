<template>
  <nav class="py-6 px-4 sm:px-6 flex items-center justify-between">
    <nuxt-link to="/" class="link">justincairns.</nuxt-link>
    <div>
      <!-- <nuxt-link to="/" class="link">blog 📚</nuxt-link> -->
      <!-- <nuxt-link to="/" class="link">components</nuxt-link> -->
    </div>
  </nav>
</template>

<script>
export default {
  components: {
    NavigationItem: () => import("../components/NavigationItem")
  }
};
</script>

<style lang="scss">
.link {
  @apply font-bold text-2xl relative mr-6;

  &:hover {
      @apply underline;
  }

  &:last-of-type {
      @apply mr-0;
  }
}
</style>