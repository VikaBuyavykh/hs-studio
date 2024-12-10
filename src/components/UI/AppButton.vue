<script setup>
defineProps({
  isThemeDark: {
    type: Boolean,
    required: false,
  },
})
</script>

<template>
  <button class="button" :class="{ 'button-dark': isThemeDark }"><slot></slot></button>
</template>

<style scoped lang="scss">
@use '@/assets/scss/fonts.scss' as *;
@use '@/assets/scss/variables.scss' as *;
@use '@/assets/scss/extensions.scss' as *;
@use '@/assets/scss/mixins.scss' as *;

.button {
  @extend %resetInputsAndBtns;
  padding: 8px 32px;
  border-radius: 30px;
  background-color: $primary2;
  @include t2(white, center);
  cursor: pointer;
  transition:
    background-color 0.3s,
    color 0.3s ease;

  &:hover {
    background-color: $primary4;
  }

  &-dark {
    &:hover {
      color: $primary2;
      background-color: $primary3;
    }
  }
}
</style>
