<script setup></script>

<template>
  <section class="stages" id="stages">
    <div class="stages--content">
      <h2 class="stages--title">Этапы работ</h2>
    </div>
  </section>
</template>

<style scoped lang="scss">
@use '@/assets/scss/fonts.scss' as *;
@use '@/assets/scss/variables.scss' as *;
@use '@/assets/scss/extensions.scss' as *;
@use '@/assets/scss/mixins.scss' as *;

.stages {
  @include size(100%, auto);
  padding-block: 60px;
  background-image: linear-gradient(rgba($primary3, 1), rgba($primary3, 0));

  &--content {
    @extend %sizing;
    height: 500px;
    padding: 60px 5%;
    @include flex(column, start, stretch, 48px);
    box-sizing: border-box;
    border: 12px solid rgba($primary4, 0.1);
    border-top-right-radius: 100px;
    border-bottom-left-radius: 100px;
  }

  &--title {
    @include h2($primary2, left);
  }
}
</style>
