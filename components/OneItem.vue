<template>
<div class="item">
  <div class="items">
    <p>{{item.id + item.itemName + item.itemDescription + item.itemUrl + item.itemPrice}}</p>


  </div>
</div>
</template>

<script>
export default {
  name: "OneItem",
  props: {
    item: {
      type: Object,
      required: true,
    }
  }
}
</script>

<style scoped>

</style>
