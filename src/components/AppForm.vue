<script setup>
import AppButton from '@/components/UI/AppButton.vue'
</script>

<template>
  <section class="form" id="form">
    <div class="form--content">
      <img class="form--image" alt="Фото интерьера" src="/Form.jpg" />
      <form class="form--form" id="request">
        <h2 class="form--form-title">Оставить заявку</h2>
        <label class="form--label">
          <span class="form--label-text">Имя</span>
          <input
            class="form--input"
            type="text"
            name="name"
            id="name"
            placeholder="Введите ваше имя"
          />
        </label>
        <label class="form--label">
          <span class="form--label-text">Почта</span>
          <input
            class="form--input"
            type="email"
            name="email"
            id="email"
            placeholder="Введите email"
          />
        </label>
        <label class="form--label">
          <span class="form--label-text">Телефон</span>
          <input
            class="form--input"
            type="tel"
            name="tel"
            id="tel"
            placeholder="Введите свой номер телефона"
          />
        </label>
        <AppButton class="form--button">Отправить</AppButton>
      </form>
    </div>
  </section>
</template>

<style scoped lang="scss">
@use '@/assets/scss/fonts.scss' as *;
@use '@/assets/scss/variables.scss' as *;
@use '@/assets/scss/extensions.scss' as *;
@use '@/assets/scss/mixins.scss' as *;

.form {
  @include size(100%, auto);
  padding-block: 60px;
  background-image: linear-gradient(rgba($primary3, 0), rgba($primary3, 1));

  &--content {
    @extend %sizing;
    display: grid;
    grid-template-rows: 1fr;
    grid-template-columns: repeat(2, 1fr);
  }

  &--image {
    @include size(100%, 100%);
    @extend %pic;
  }

  &--form {
    @include size(80%, auto);
    padding: 60px 10% 70px;
    @include flex(column, start, start, 24px);
    //background-color: rgba($primary4, 0.8);
    background-image: url('/back.jpg');
    @extend %bgi;

    &-title {
      @include h2(white, left);
      font-weight: 400;
    }
  }

  &--label {
    @include size(100%, auto);
    padding-block: 8px;
    @include flex(column, start, stretch, 8px);
    border-bottom: 1px solid white;

    &-text {
      @include p3(white, left);
    }

    .form--input {
      @include t2(white, left);
      @extend %resetInputsAndBtns;

      &::placeholder {
        @include t2(rgba(white, 0.5), left);
      }
    }
  }
}

.form--button {
  margin-top: 16px;
  align-self: end;
}
</style>
