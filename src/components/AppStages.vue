<script setup></script>

<template>
  <section class="stages" id="stages">Stages</section>
</template>

<style scoped lang="scss">
@use '@/assets/scss/fonts.scss' as *;
@use '@/assets/scss/variables.scss' as *;
@use '@/assets/scss/extensions.scss' as *;
@use '@/assets/scss/mixins.scss' as *;

.stages {
  @include size(100%, 500px);
  background-image: linear-gradient(rgba($primary3, 1), rgba($primary3, 0));
  outline: 1px solid red;
}
</style>
