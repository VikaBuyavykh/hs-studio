<script setup>
import AppButton from '@/components/UI/AppButton.vue'

function scrollToForm() {
  console.log('kkk')

  document.querySelector('#form').scrollIntoView({ behavior: 'smooth', block: 'start' })
}
</script>

<template>
  <section class="cover" id="cover">
    <div class="cover--overlay">
      <div class="cover--content">
        <div class="cover--content-box">
          <p class="cover--desc">Hs-Studio</p>
          <h1 class="cover--title">Студия хоумстейджинга Надежды Буявых</h1>
          <span class="cover--line"></span>
          <AppButton @click="scrollToForm">Оставить заявку</AppButton>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped lang="scss">
@use '@/assets/scss/fonts.scss' as *;
@use '@/assets/scss/variables.scss' as *;
@use '@/assets/scss/extensions.scss' as *;
@use '@/assets/scss/mixins.scss' as *;

.cover {
  @include size(100%, auto);
  background-image: url('/Banner.jpg');
  @extend %bgi;

  &--overlay {
    @include size(100%, 100%);
    padding-block: 16% 20%;
    background-image: linear-gradient(
      rgba($primary3, 0) 60%,
      rgba($primary3, 0.9) 80%,
      rgba($primary3, 1)
    );
  }

  &--content {
    @extend %sizing;

    &-box {
      width: 60%;
      @include flex(column, start, center, 6px);
    }
  }

  &--desc {
    @include p1($primary2, center);
  }

  &--title {
    @include h1($primary2, center);
    margin-bottom: 16px;
  }

  &--line {
    margin-bottom: 30px;
    @include size(40%, 1px);
    background-color: $primary2;
  }
}
</style>
