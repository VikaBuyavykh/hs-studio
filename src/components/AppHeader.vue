<script setup></script>

<template>
  <header class="header">
    <h1 class="header--title">Надежда Буявых</h1>
  </header>
</template>

<style scoped lang="scss">
@use '@/assets/scss/fonts.scss' as *;
@use '@/assets/scss/variables.scss' as *;

.header {
  background-color: $primary1;
  padding-block: 100px;

  &--title {
    margin-inline: auto;
    @include h1($primary3, center);
  }
}
</style>
