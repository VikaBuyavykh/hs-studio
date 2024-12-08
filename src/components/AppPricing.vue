<script setup></script>

<template>
  <section class="pricing" id="pricing">Pricing</section>
</template>

<style scoped lang="scss">
@use '@/assets/scss/fonts.scss' as *;
@use '@/assets/scss/variables.scss' as *;
@use '@/assets/scss/extensions.scss' as *;
@use '@/assets/scss/mixins.scss' as *;

.pricing {
  @include size(100%, 500px);
  outline: 1px solid red;
}
</style>
