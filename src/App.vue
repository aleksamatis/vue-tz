<script setup>
import ItemList from './components/ItemList.vue'
import ItemCard from './components/ItemCard.vue'
</script>

<template>
<div class="main-container">
  <div>
  <ItemList :items="leftSelectedItems">
    Items count: {{leftSelectedItems.length}}/6
  </ItemList>
  <ItemList :items="leftItems" @item-selected="onItemSelectedLeft"/>
  </div>
  <div>
  <ItemCard :item="selectedItem" v-if="selectedItem"/>
  <ItemList :items="rightItems" @item-selected="onItemSelected"/>
  </div>
</div>
</template>

<script>

export default {
    data() {
       return {
            leftItems: [{
        "id": 1,
        "name": "Shoes 1"
    },
    {
        "id": 2,
        "name": "Shoes 2"
    },
    {
        "id": 3,
        "name": "Shoes 3"
    },
    {
        "id": 4,
        "name": "Shoes 4"
    },
    {
        "id": 5,
        "name": "T-shirt 1"
    },
    {
        "id": 6,
        "name": "T-shirt 2"
    },
    {
        "id": 7,
        "name": "T-shirt 3"
    },
    {
        "id": 8,
        "name": "T-shirt 4"
    }], 
    rightItems:[
    {
        "id": 11,
        "name": "Jacket 1"
    },
    {
        "id": 12,
        "name": "Jacket 2"
    },
    {
        "id": 13,
        "name": "Jacket 3"
    },
    {
        "id": 14,
        "name": "Jacket 4"
    },
    {
        "id": 15,
        "name": "Hoodie 1"
    },
    {
        "id": 16,
        "name": "Hoodie 2"
    },
    {
        "id": 17,
        "name": "Hoodie 3"
    },
    {
        "id": 18,
        "name": "Hoodie 4"
    }
    ], selectedItem: null,
    leftSelectedItems: [],
        }
        
    },

    mounted() {
      this.selectedItem = this.rightItems[0]
    },
  
  methods: {
    onItemSelected(item) {
      this.selectedItem = item,
      this.selectedItem = leftSelectedItems.push[item]
    },
     onItemSelectedLeft(item) {
      if (this.leftSelectedItems.find(i => i.id === item.id)) {
        return
      }
      this.leftSelectedItems.push(item)
      if (this.leftSelectedItems.length == 7){
        this.leftSelectedItems.shift()
      }
    }
  }
}
</script>
<style scoped>
.main-container{
    border: 1px solid red; display: flex; gap: 100px;
}
</style>
