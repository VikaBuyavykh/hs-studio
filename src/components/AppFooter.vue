<script setup>
const links = [
  {
    name: 'Работа в компании',
    link: '#',
  },
  {
    name: 'Условия пользования',
    link: '#',
  },
  {
    name: 'Выходные данные',
    link: '#',
  },
  {
    name: 'Политика конфиденциальности',
    link: '#',
  },
  {
    name: 'Карта сайта',
    link: '#',
  },
]
const socials = [
  {
    name: 'facebook',
    image: '/fb.svg',
  },
  {
    name: 'twitter',
    image: '/tw.svg',
  },
  {
    name: 'linkedIn',
    image: '/in.svg',
  },
  {
    name: 'instagram',
    image: '/ig.svg',
  },
]
</script>

<template>
  <footer class="footer" id="footer">
    <div class="footer--content">
      <nav class="footer--nav">
        <a class="footer--link" v-for="item in links" :key="item.name" :href="item.link">{{
          item.name
        }}</a>
      </nav>
      <div class="footer--info">
        <div class="footer--logo">
          <img src="/Logo.png" alt="Logo" class="footer--logo-img" />
          <p class="footer--logo-text">hs-studio</p>
        </div>
        <address class="footer--contacts">
          <p class="footer--title">Контакты</p>
          <ul class="footer--list">
            <li class="footer--list-item">
              <a href="mailto:your-adress@example.com">
                your-adress@example.com
                <div>
                  <img src="/mail.svg" alt="Иконка почты" />
                </div>
              </a>
            </li>
            <li class="footer--list-item">
              <a href="tel:+79123456789">
                +7(912)345-67-89
                <div>
                  <img src="/tel.svg" alt="Иконка телефона" />
                </div>
              </a>
            </li>
          </ul>
          <ul class="footer--socials">
            <li v-for="item in socials" :key="item.name">
              <a href="#">
                <img :src="item.image" :alt="item.name" />
              </a>
            </li>
          </ul>
        </address>
      </div>
    </div>
  </footer>
</template>

<style scoped lang="scss">
@use '@/assets/scss/fonts.scss' as *;
@use '@/assets/scss/variables.scss' as *;
@use '@/assets/scss/extensions.scss' as *;
@use '@/assets/scss/mixins.scss' as *;

.footer {
  @include size(100%, auto);
  padding-block: 60px;
  background-color: $primary3;

  &--content {
    @extend %sizing;
    border-top: 1px solid $primary2;
    padding-top: 40px;
    @include flex(column, start, stretch, 60px);
  }

  &--nav {
    @include size(100%, auto);
    @include flex(row, space-between, center, 16px);
  }

  &--link {
    text-decoration: none;
    @include p3($primary2, center);
    opacity: 1;
    transition: opacity 0.3s ease;

    &:hover {
      opacity: 0.5;
    }
  }

  &--info {
    @include size(100%, auto);
    display: grid;
    grid-template-rows: 1fr;
    grid-template-columns: repeat(2, 1fr);
  }

  &--logo {
    margin-block: auto;
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

  &--contacts {
    @include size(100%, auto);
    @include flex(column, start, end, 20px);
    font-style: normal;
  }

  &--title {
    @include p1($primary2, left);
    border-bottom: 1px solid $primary1;
  }

  &--list,
  &--socials {
    @include size(100%, auto);
    margin: 0;
    padding: 0;
    list-style-type: none;
  }

  &--list {
    @include flex(column, start, end, 16px);

    &-item {
      a {
        text-decoration: none;
        @include p3($primary2, left);
        @include flex(row, end, center, 8px);
        transition: color 0.3s ease;

        &:hover {
          color: $primary1;
        }

        &:hover div {
          opacity: 0.5;
        }

        div {
          @include size(20px, 20px);
          border-radius: 50%;
          background-color: white;
          @include flex(row, center, center, 0);
          opacity: 1;
          transition: opacity 0.3s ease;

          img {
            @include size(12px, 12px);
          }
        }
      }
    }
  }

  &--socials {
    @include flex(row, end, center, 20px);

    a {
      opacity: 1;
      transition: opacity 0.3s ease;

      &:hover {
        opacity: 0.5;
      }

      img {
        @include size(18px, 18px);
      }
    }
  }
}
</style>
