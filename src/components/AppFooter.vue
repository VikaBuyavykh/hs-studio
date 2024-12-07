<script setup></script>

<template>
  <footer class="footer" id="footer">Footer</footer>
</template>

<style scoped lang="scss">
@use '@/assets/scss/fonts.scss' as *;
@use '@/assets/scss/variables.scss' as *;
@use '@/assets/scss/extensions.scss' as *;
@use '@/assets/scss/mixins.scss' as *;

.footer {
  @include size(100%, 500px);
  outline: 1px solid red;
}
</style>
