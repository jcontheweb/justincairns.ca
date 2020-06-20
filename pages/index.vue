<template>
  <div>
    <Hero />
    <ItemList />
  </div>
</template>

<script>
import ItemList from '~/components/ItemList.vue'
import Hero from '~/components/Hero.vue'

export default {
  components: {
    ItemList,
    Hero
  }
}
</script>