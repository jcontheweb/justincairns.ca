<template>
  <div class="font-sans flex flex-col tracking-tight min-h-screen overflow-x-hidden text-gray-900">
    <div class="max-w-6xl mx-auto">
      <Header />
      <nuxt class="flex-1 px-4 sm:px-6 mt-6" />
    </div>
    <Footer class="mt-8 sm:mt-16" />
  </div>
</template>

<script>
export default {
  components: {
    Footer: () => import("~/components/Footer"),
    Header: () => import("~/components/Header")
  }
};
</script>

<style lang="scss">
::-webkit-scrollbar {
  width: 6px;
}
::-webkit-scrollbar-track {
  border-radius: 70px;
}
::-webkit-scrollbar-thumb {
  background: rgba(0, 0, 0, 0.32);
  border-radius: 72px;
}
</style>