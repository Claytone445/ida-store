<template>
  <form @submit.prevent="checkForm">
  <div class="form" >
    <div class="form__item">
    <label for="itemName" class="form__label">Наименование товара<span>*</span></label>
    <input
      id ="itemName"
      placeholder="Введите наименование товара"
      class="form__input"
      v-model.trim="form.itemName"
      :class="$v.form.itemName.$error ? 'is-invalid' : ''"

    >
      <p v-if="$v.form.itemName.$dirty && !$v.form.itemName.required" class="invalid-feedback">
        Поле является обязательным
      </p>
    </div>
    <div class="form__item">
    <label for="itemDescription" class="form__description-label"><span>Описание товара</span></label>
    <textarea
      id="itemDescription"
      placeholder="Введите описание товара"
      name="description"
      class="form__description"
      v-model.trim="form.itemDescription"
      :class="$v.form.itemDescription.$error ? 'is-invalid' : ''"
    ></textarea>
      <p v-if="$v.form.itemDescription.$dirty && !$v.form.itemName.required" class="invalid-feedback">
        Поле является обязательным
      </p>
    </div>
    <div class="form__item">
      <label for="imageUrl" class="form__label">Ссылка на изображение товара<span>*</span></label>
      <input id ="imageUrl"  placeholder="Введите ссылку"  class="form__input"
      v-model.trim="form.itemUrl">
    </div>
    <div class="form__item">
      <label for="itemPrice" class="form__label">Цена товара<span>*</span></label>
      <input
        id ="itemPrice"
        placeholder="Введите цену"
        class="form__input"
        v-model.trim="form.itemPrice"
        :class="$v.form.itemPrice.$error ? 'is-invalid' : ''"
        value="priceMask"
      >
      <p v-if="$v.form.itemPrice.$dirty && !$v.form.itemPrice.required" class="invalid-feedback">
        Поле является обязательным
      </p>
    </div>
    <div class="form__item">
      <button type="submit" class="form__btn">Добавить Товар</button>
    </div>
  </div>
  </form>
</template>

<script>
import { required} from 'vuelidate/lib/validators'

export default {
  name: 'AddItem',
  data () {
    return {
      form: {
        itemName: '',
        itemDescription: "",
        itemUrl: "",
        itemPrice: "",
      },
    }
  },
  validations: {
    form: {
      itemName: {required},
      itemDescription: {required},
      itemUrl: {required},
      itemPrice: {required},
    }
  },
  methods: {
    checkForm() {
      this.$v.form.$touch()
      if (!this.$v.form.$error) {
        console.log('Валидация прошла успешно')
      }
    }
  },
  computed: {
    priceMask() {
      return this.itemPrice.toString().replace(/\B(?=(\d{3})+(?!\d))/g, " ")
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

.is-invalid {
  color: red;
}

.invalid-feedback {
  margin-top: 4px;
  font-family: 'Source Sans Pro', sans-serif;
  font-weight: 400;
  font-size: 8px;
  color: red;
}

.form {
  display: flex;
  flex-direction: column;
  max-width: 332px;
  background-color: $formBG;
  box-shadow: 0px 20px 30px rgba(0, 0, 0, 0.04), 0 6px 10px rgba(0, 0, 0, 0.02);
  padding: 24px 24px 24px 24px;
  border-radius: 4px;
  @media  screen and (max-width: 375px) {
    padding: 24px 12px 24px 12px;
  }
  &__item {
    margin-bottom: 24px;
  }
  &__item:last-child {
    margin: 0px;
  }
  &__label {
    display: block;
    font-weight: 400;
    font-size: 10px;
    line-height: 13px;
    font-family: 'Source Sans Pro', sans-serif;
    margin-bottom: 4px;
  }
  &__label span {
    color:$labelSpan;
  }
  &__input {
    padding-left: 16px;
    height: 36px;
    width: 284px;
    outline: none;
    transition: all 0.5s ease 0s;
    font-family: 'Source Sans Pro', sans-serif;
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
    width: 100%;
    resize: none;
    min-height: 100px;
    outline: none;
    font-family: 'Source Sans Pro', sans-serif;
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

  &__description-label span {
    font-weight: 400;
    font-size: 10px;
    line-height: 13px
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
   box-shadow: 0px 2px 5px rgba(0, 0, 0, 0.1);
   color: $btnFont;
 }
  &__btn:hover {
    cursor: pointer;
    transition: all 0.5s ease 0s;
    background-color: $btnHoverBG;
    color: $btnHoverFont;
  }
}
</style>


