<script setup>
const links = [
  {
    href: '#cover',
    name: 'Главная',
  },
  {
    href: '#advantages',
    name: 'Преимущества',
  },
  {
    href: '#',
    name: 'Портфолио',
  },
  {
    href: '#',
    name: 'Этапы',
  },
  {
    href: '#',
    name: 'Команда',
  },
  {
    href: '#footer',
    name: 'Контакты',
  },
]
</script>

<template>
  <header class="header">
    <div class="header--logo">
      <img src="/Logo.png" alt="Logo" class="header--logo-img" />
      <p class="header--logo-text">hs-studio</p>
    </div>
    <nav class="header--nav">
      <a v-for="link in links" :key="link.name" :href="link.href" class="header--nav-link">{{
        link.name
      }}</a>
    </nav>
  </header>
</template>

<style scoped lang="scss">
@use '@/assets/scss/fonts.scss' as *;
@use '@/assets/scss/variables.scss' as *;
@use '@/assets/scss/extensions.scss' as *;
@use '@/assets/scss/mixins.scss' as *;

.header {
  @extend %sizing;
  padding-block: 45px;
  @include flex(row, space-between, center, 30px);

  &--logo {
    @include flex(row, start, center, 10px);

    &-img {
      @include size(20px, 20px);
      object-position: center;
      object-fit: contain;
    }

    &-text {
      @include p1($primary2, left);
    }
  }

  &--nav {
    @include flex(row, end, center, 30px);

    &-link {
      @include t2($primary2, right);
      text-decoration: none;
      transition: opacity 0.3s ease;

      &:hover {
        opacity: 0.5;
      }
    }
  }
}
</style>
