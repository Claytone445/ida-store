<template>
  <div class="items__wrapper">
      <div class="items__img"><img :src="item.itemUrl" alt="" class="items__picture">
        <img src="~assets/img/basket.png" alt="" class="items__basket">
      </div>
      <div class="items__description">
        <h2 class="items__title">{{item.itemName}}</h2>
        <p class="items__info">{{item.itemDescription}}</p>
        <p class="items__price">{{item.itemPrice}} руб.</p>
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

<style lang="scss" scoped>

@import "~assets/scss/variables";

</style>
