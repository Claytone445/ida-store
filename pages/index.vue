<template>
  <div class="main">
    <div class="container">
      <h1>Добавление товара</h1>
      <select class="container__select">
        <option>От меньшего к большему</option>
        <option>От большего к меньшему</option>
        <option>По наименованию</option>
      </select>
    </div>
    <div class="container__components">
      <add-item />
      <store-items/>
    </div>
  </div>




</template>

<script>
export default {
  name: 'IndexPage',
}
</script>

<style lang="scss">
@import "~assets/scss/variables";

body {
  box-sizing: border-box;
  padding: 0;
  margin: 0;
  display: flex;
  justify-content: center;
}

h1 {
  margin: 0;
  font-family: 'Source Sans Pro';
  font-style: normal;
  font-weight: 600;
  font-size: 28px;
  line-height: 35px;
  color: #3F3F3F;
}

.main {
  margin: 32px;
  width: 1440px;
  background-color: $mainBG;
}

.container {
  padding: 32px 32px 16px 32px;
  display: flex;
  justify-content: space-between;
  &__select {
    appearance: none;
    padding: 16px;
    box-shadow: 0px 2px 5px rgba(0, 0, 0, 0.1);
    color: $select;
    font-size: 12px;
    font-weight: 400;
    border-radius: 4px;
    border-color: white;
    background: url("assets/img/selectArrow.png") no-repeat right;
    background-position-x: calc(100% - 6px);
    background-color: white;
    text-align: center;
  }


  &__components {
    margin: 32px;
    display: flex;
    justify-content: space-between;
  }
}
</style>
