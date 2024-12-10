<script setup>
const advantages = [
  {
    title: 'Project Plan',
    desc: 'There are many variations of the passages of lorem Ipsum from available, majority.',
  },
  {
    title: 'Interior Work',
    desc: 'There are many variations of the passages of lorem Ipsum from available, majority.',
  },
  {
    title: 'Realization',
    desc: 'There are many variations of the passages of lorem Ipsum from available, majority.',
  },
]
</script>

<template>
  <section class="advantages" id="advantages">
    <div class="advantages--content">
      <h2 class="advantages--title">Наши преимущества</h2>
      <ul class="advantages--list">
        <li v-for="item in advantages" :key="item.title" class="advantages--item">
          <p class="advantages--item-title">{{ item.title }}</p>
          <span class="advantages--item-desc">{{ item.desc }}</span>
        </li>
      </ul>
    </div>
  </section>
</template>

<style scoped lang="scss">
@use '@/assets/scss/fonts.scss' as *;
@use '@/assets/scss/variables.scss' as *;
@use '@/assets/scss/extensions.scss' as *;
@use '@/assets/scss/mixins.scss' as *;

.advantages {
  @include size(100%, auto);
  background-color: $primary3;

  &--content {
    @extend %sizing;
    padding-block: 60px;
    @include flex(column, start, stretch, 24px);
  }

  &--title {
    @include h2($primary2, center);
  }

  &--list {
    list-style-type: none;
    margin: 0;
    padding: 0;
    @include flex(row, space-between, stretch, 30px);
  }

  &--item {
    padding: 30px;
    @include flex(column, start, start, 12px);
    background-image: radial-gradient(white 0%, $primary3 60%);

    &-title {
      width: 100%;
      @include p2($primary2, center);
    }

    &-desc {
      @include t2($primary2, center);
    }
  }
}
</style>
