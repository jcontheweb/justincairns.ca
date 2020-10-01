<template>
  <div>
    <!-- <Hero />
    <ItemList /> -->
    <Modal>
      <form @submit.prevent="create">
        <label for="">Company name</label>
        <input type="text">
        <button>Create</button>
      </form>
    </Modal>
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