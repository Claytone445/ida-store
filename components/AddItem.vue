<!-- Please remove this file from your project -->
<template>
  <div class="form">
    <div class="form__item">
    <label for="itemName" class="form__label">Наименование товара<span>*</span></label>
    <input id ="itemName" placeholder="Введите наименование товара" type="text" class="form__input">
    </div>
    <div class="form__item">
    <label for="itemDescription" class="form__description-label">Описание товара</label>
    <textarea id="itemDescription"  placeholder="Введите описание товара" name="description"  class="form__description"></textarea>
    </div>
    <div class="form__item">
      <label for="imageUrl" class="form__label">Ссылка на изображение товара<span>*</span></label>
      <input id ="imageUrl"  placeholder="Введите ссылку" type="url" class="form__input">
    </div>
    <div class="form__item">
      <label for="itemPrice" class="form__label">Цена товара<span>*</span></label>
      <input id ="itemPrice" placeholder="Введите цену" type="number" class="form__input">
    </div>
    <div class="form__item">
      <button class="form__btn">Добавить Товар</button>
    </div>
  </div>
</template>

<script>
export default {
  name: 'AddItem',
}
</script>

<style lang="scss">
* {
  padding: 0;
  margin: 0;
}



@import "~assets/scss/variables";
.form {
  display: flex;
  flex-direction: column;
  max-width: 332px;
  background-color: $formBG;
  box-shadow: 0px 20px 30px rgba(0, 0, 0, 0.04), 0px 6px 10px rgba(0, 0, 0, 0.02);
  padding: 24px;
  border-radius: 4px;

  &__item {
    margin-bottom: 32px;
  }
  &__item:last-child {
    margin: 0px;
  }
  &__label {
    display: block;
    font-weight: 400;
    font-size: 10px;
    line-height: 13px;
    color: $label;
    margin-bottom: 4px;
  }
  &__label span {
    color:$labelSpan;
  }
  &__input {
    padding-left: 16px;
    height: 36px;
    max-width: 278px;
    width: 100%;
    outline: none;
    transition: all 0.5s ease 0s;
    font-weight: 400;
    font-size: 12px;
    line-height: 15px;
    box-shadow: 0px 2px 5px rgba(0, 0, 0, 0.1);
    border: white;
    border-radius: 4px;
  }
  &__input:focus {
    box-shadow: 0 0 15px #fff;
  }

  &__description {
    padding: 10px 0 0 16px;
    max-width: 278px;
    width: 100%;
    resize: none;
    min-height: 100px;
    outline: none;
    font-weight: 400;
    font-size: 12px;
    line-height: 15px;
    box-shadow: 0px 2px 5px rgba(0, 0, 0, 0.1);
    border: white;
    border-radius: 4px;
    transition: all 0.5s ease 0s;
  }
 &__description:focus {
   box-shadow: 0 0 15px #fff;
 }

 &__btn {
   min-height: 36px;
   width: 100%;
   outline: none;
   border: white;
   border-radius: 10px;
   background-color: $btnBG;
   font-weight: 600;
   font-size: 12px;
   line-height: 15px;
   color: $btnFont;
 }
}
</style>


