<template>
    <div class="main">
    <div class="container">
  <add-item
    @addWare="addWare"
  />
<div class="items">
  <div class="items__wrapper">
    <div class="items__img"><img src="~assets/img/camera.png" alt="" class="items__picture">
      <img src="~assets/img/basket.png" alt="" class="items__basket">
    </div>
    <div class="items__description">
      <h2 class="items__title">Наименование Товара</h2>
      <p class="items__info">Довольно-таки интересное описание товара в несколько строк. Довольно-таки интересное описание товара в несколько строк</p>
      <p class="items__price">10 000 руб.</p>
    </div>
  </div>
  <div class="items__wrapper">
    <div class="items__img"><img src="~assets/img/camera.png" alt="" class="items__picture">
      <img src="~assets/img/basket.png" alt="" class="items__basket">
    </div>
    <div class="items__description">
      <h2 class="items__title">Наименование Товара</h2>
      <p class="items__info">Довольно-таки интересное описание товара в несколько строк. Довольно-таки интересное описание товара в несколько строк</p>
      <p class="items__price">10 000 руб.</p>
    </div>
  </div>
    <one-item
      v-for="item in items" :key="item.id"
      :item="item"
    />
 </div>
</div>
</div>
</template>

<script>
import addItem from "~/components/AddItem";
import oneItem from "~/components/OneItem";

export default {
  name: "StoreItems",
  components: {
    addItem, oneItem
  },
  data() {
    return {
      items: [
        {
          itemName: "Добавленный товар",
          itemDescription: "Довольно-таки интересное описание товара в несколько строк. Довольно-таки интересное описание товара в несколько строк",
          itemUrl: "https://klike.net/uploads/posts/2021-01/1611131113_2.jpg",
          itemPrice: 100},
      ],
    }
  },
  methods: {
  addWare(ware) {
    this.items.push(ware);
  }
  }
}
</script>

<style lang="scss">

@import "~assets/scss/variables";

* {
  padding: 0;
  margin: 0;
  box-sizing: border-box;
}

.main {
  max-width: 1440px;
  margin: 0 auto;
}

.container {
  display: flex;
  justify-content: space-between;
  @media screen and (max-width: 720px) {
    flex-direction: column;
  }
}

.items {
  max-width: 1044px;
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  @media  screen and (max-width: 720px) {
    flex-direction: column;
    max-width: 332px;
    margin-top: 24px;
  }

  &__wrapper {
    min-width: 332px;
    min-height: 422px;
    position: relative;
    border-radius: 4px;
    display: flex;
    flex-direction: column;
    margin: 0 0 16px 16px;
    @media  screen and (max-width: 720px) {
    margin: 0 0 16px 0;
    }
  }

  &__picture {
    display: block;
    object-fit: cover;
    width: 100%;
    height: 100%;
    cursor: pointer;
    max-width: 332px;
    max-height: 200px;
  }


  &__basket {
    content: "";
    position: absolute;
    top: -3%;
    right: -3%;
  }

  &__description {
    padding: 16px 16px 24px 16px;
    background-color: $formBG;
    background-size: 100%;
  }
  &__title {
    font-family: 'Source Sans Pro';
    font-style: normal;
    font-weight: 600;
    font-size: 20px;
    line-height: 25px;
    margin-bottom: 16px;
    color: $items;
  }
  &__info {
    margin-bottom: 32px;
    font-family: 'Source Sans Pro';
    font-style: normal;
    font-weight: 400;
    font-size: 16px;
    line-height: 20px;
    color: $items;
    max-width: 300px;
  }

  &__price {
    font-family: 'Source Sans Pro';
    font-style: normal;
    font-weight: 600;
    font-size: 24px;
    line-height: 30px;
    color: $items;
  }

}
</style>
