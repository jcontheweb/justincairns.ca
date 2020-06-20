<template>
  <div class="bg-gray-100 border-t fixed bottom-0 inset-x-0" :class="{ 'p-4 sm:p-8': expanded }">
    <button
      v-if="!expanded"
      @click="expanded = true"
      class="flex justify-between items-center w-full p-4"
    >
      <p class="font-medium">Project Details</p>
      <SvgChevronUp />
    </button>
    <button v-else @click="expanded = false" class="p-4 absolute right-0 top-0">
      <SvgChevronDown />
    </button>
    <div v-show="expanded">
      <slot />
    </div>
  </div>
</template>

<script>
export default {
  components: {
    SvgChevronUp: () => import("~/components/Svg/SvgChevronDown"),
    SvgChevronDown: () => import("~/components/Svg/SvgChevronUp")
  },
  data: () => ({ expanded: true })
};
</script>

<style lang="scss">
</style>