<template>
  <div class="main">
    <div class="main-item">
      <ItemCard class="main-item1" v-for="item in items" @click="$emit('item-selected', item)" :key="item.id" :item="item"></ItemCard>
    </div>
    <slot />
  </div>
</template>


<script>
import ItemCard from './ItemCard.vue'
  
  export default {
    components: {
      ItemCard
    },
    props: {
      items: {
        type: Array
      }
    }
  }
</script>

<style scoped>
  .main {
    margin: 0 auto;
    border: 3px solid #000;
  }

  .main-item {
    display: flex;
    flex-wrap: wrap;
    justify-content: flex-start;
    gap: 20px;
    padding: 20px;
  }

  .main-item1 {
    display: flex;
    border: 3px solid #000;
    padding: 20px;
  }
</style>