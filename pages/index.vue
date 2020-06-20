<template>
  <div>
    <Hero />
    <ItemList />
  </div>
</template>

<script>
export default {
  components: {
    ItemList: () => import('~/components/ItemList.vue'),
    Hero: () => import('~/components/Hero.vue')
  }
}
</script>