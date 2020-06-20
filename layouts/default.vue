<template>
  <div class="font-sans flex flex-col tracking-tight min-h-screen overflow-x-hidden text-gray-900">
    <div class="max-w-6xl mx-auto">
      <Header />
      <transition name="page" mode="out-in">
        <nuxt class="flex-1 px-4 sm:px-6 mt-6" />
      </transition>
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
.page-enter-active,
.page-leave-active {
  transition: all 400ms ease;
}

.page-enter,
.page-leave-active {
  opacity: 0;
  transform: translateX(-8px);
}

.fade-enter-active {
  transition: all 300ms ease;
}

.fade-enter,
.fade-leave-active {
  transform: translateY(-16px);
}

.modal-accordion-enter-active,
.modal-accordion-leave-active {
  max-height: 1000px;
  transition: all 300ms ease;
}

.modal-accordion-enter,
.modal-accordion-leave-active {
  max-height: 0;
}

::-webkit-scrollbar {
    width: 6px;
  }
  ::-webkit-scrollbar-track {
    border-radius: 70px;
  }
  ::-webkit-scrollbar-thumb {
    background: rgba(0,0,0, .32);
    border-radius: 72px;
  }
</style>