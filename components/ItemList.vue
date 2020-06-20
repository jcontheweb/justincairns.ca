<template>
  <div class="mt-8 sm:mt-16 grid grid-cols-1 sm:grid-cols-2 gap-3">
    <Item
      v-for="(item, index) in items"
      :key="index"
      :image="item.image"
      :title="item.title"
      :company="item.company"
      :technologies="item.technology"
      :description="item.description"
      :displays="item.displays"
      :contributions="item.contributions"
      :type="item.type"
      :url="item.url"
    />
  </div>
</template>

<script>
import items from "~/static/data/portfolio.json"
export default {
  components: {
    Item: () => import("~/components/Item.vue")
  },
  data: () => ({ items })
};
</script>