<template>
  <div class="main">
    <div class="container">
      <h1>Добавление товара</h1>
      <select class="container__select">
        <option>По возрастанию</option>
        <option>По уменьшению</option>
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

@import url('https://fonts.googleapis.com/css2?family=Source+Sans+Pro&display=swap');
@import "~assets/scss/variables";

body {
  box-sizing: border-box;
  padding: 0;
  margin: 0;
  background-color: $mainBG;
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
  margin: 0px 32px;
  max-width: 1440px;
  margin: 0 auto;
}

.container {
  padding: 32px 32px 16px 32px;
  display: flex;
  justify-content: space-between;
  @media  screen and (max-width: 720px) {
    flex-direction: column;
  }
  &__select {
    appearance: none;
    padding: 10px 25px 10px 16px;
    box-shadow: 0px 2px 5px rgba(0, 0, 0, 0.1);
    color: $select;
    font-size: 12px;
    font-weight: 400;
    border-radius: 4px;
    border-color: white;
    background: url("assets/img/selectArrow.png") no-repeat right;
    background-position-x: calc(100% - 10%);
    background-color: white;
    text-align: center;
    @media  screen and (max-width: 720px) {
      margin: 10px 0;
      max-width: 332px;
    }
  }


  &__components {
    margin: 32px;
    display: flex;
    justify-content: space-between;
    @media  screen and (max-width: 720px) {
      flex-direction: column;
      margin: 8px 32px;
    }
  }
}
</style>
