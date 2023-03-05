<template>
<div>
  <div class="main-item">
    <div class="main-item1">{{item.name}}</div>
  </div>
</div>
</template>

<script>
export default {
  props: {
    item: {
      type: Object
    }
  }
}
</script>

<style scoped>
.main-item {
  display: flex;
  justify-content: flex-start;
  padding: 20px;
}
.main-item1 {
  display: flex;
  border: 3px solid #ff1414;
  padding: 20px;
}
</style>