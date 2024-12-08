<script setup></script>

<template>
  <section class="projects" id="projects">Projects</section>
</template>

<style scoped lang="scss">
@use '@/assets/scss/fonts.scss' as *;
@use '@/assets/scss/variables.scss' as *;
@use '@/assets/scss/extensions.scss' as *;
@use '@/assets/scss/mixins.scss' as *;

.projects {
  @include size(100%, 500px);
  background-color: $primary3;
  outline: 1px solid red;
}
</style>
