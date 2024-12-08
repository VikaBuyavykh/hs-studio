<script setup>
import { team } from '@/utils/team'
import { useRoute } from 'vue-router'
const route = useRoute()
const person = team.find((item) => item.id == route.params.id)
const bio = [
  'Lorem ipsum dolor sit amet, adipiscing Aliquam eu sem vitae turpmaximus.posuere in.Contrary to popular belief.There are many variations of passages of Lorem Ipsum available, but the majority have suffered alteration in some form, njecthumour randomised words which dont look even slightly believable.',
  'Embarrassing hidden in the middle of text. All the Lorem Ipsum generators on the Internet tend to repeat predefined but the majority have suffered alteration in some form chunks as necessary',
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
  <section class="questionnaire">
    <div class="questionnaire--cover">
      <div class="questionnaire--cover-content">
        <h1 class="questionnaire--cover-title">Команда</h1>
        <p class="questionnaire--cover-subtitle">Professional Single</p>
      </div>
    </div>
    <article class="questionnaire--content">
      <div class="questionnaire--info">
        <img class="questionnaire--info-img" :alt="person.name" :src="person.image" />
        <div class="questionnaire--info-box">
          <h2 class="questionnaire--name">{{ person.name }}</h2>
          <p class="questionnaire--occupation">{{ person.occupation }}</p>
          <p class="questionnaire--desc">
            Lorem ipsum dolor sit amet, adipiscing Aliquam eu sem vitae turpmaximus.posuere
            in.Contrpobelie frandomised words which don't look even slightly believable.
          </p>
          <ul class="questionnaire--contacts">
            <li class="questionnaire--contacts-item">
              <a href="mailto:your-adress@example.com">
                <div>
                  <img src="/mail.svg" alt="Иконка почты" />
                </div>
                your-adress@example.com
              </a>
            </li>
            <li class="questionnaire--contacts-item">
              <a href="tel:+79123456789">
                <div>
                  <img src="/tel.svg" alt="Иконка телефона" />
                </div>
                +7(912)345-67-89
              </a>
            </li>
          </ul>
          <ul class="questionnaire--socials">
            <li v-for="item in socials" :key="item.name">
              <a href="#">
                <img :src="item.image" :alt="item.name" />
              </a>
            </li>
          </ul>
        </div>
      </div>
      <div class="questionnaire--bio">
        <h2 class="questionnaire--bio-title">Биография</h2>
        <p v-for="(item, index) in bio" :key="index" class="questionnaire--bio-text">{{ item }}</p>
      </div>
    </article>
  </section>
</template>

<style lang="scss" scoped>
@use '@/assets/scss/fonts.scss' as *;
@use '@/assets/scss/variables.scss' as *;
@use '@/assets/scss/extensions.scss' as *;
@use '@/assets/scss/mixins.scss' as *;

.questionnaire {
  @include size(100%, auto);
  @include flex(column, start, stretch, 0);
  background-image: linear-gradient(white 50%, rgba($primary3, 1));

  &--cover {
    @include size(100%, 300px);
    background-image: url('/cover2.png');
    @extend %bgi;
    @include flex(column, end, center, 0);

    &-content {
      @include size(90%, auto);
      max-width: 500px;
      padding-block: 24px;
      border-top-left-radius: 30px;
      border-top-right-radius: 30px;
      @include flex(column, start, center, 10px);
      background-color: white;
    }

    &-title {
      @include h2($primary2, center);
    }

    &-subtitle {
      @include t1($primary2, center);
    }
  }

  &--content {
    @extend %sizing;
    padding-top: 60px;
    @include flex(column, start, stretch, 30px);
  }

  &--info {
    @include size(100%, auto);
    display: grid;
    grid-template-rows: 1fr;
    grid-template-columns: 1fr 2fr;
    gap: 30px;

    &-img {
      @include size(100%, 500px);
      @extend %pic;
      border-radius: 30px;
    }

    &-box {
      @include size(100%, auto);
      @include flex(column, center, start, 10px);

      .questionnaire--name {
        @include h2($primary2, left);
      }

      .questionnaire--occupation {
        @include p3($primary2, left);
        margin-bottom: 12px;
      }

      .questionnaire--desc {
        @include t2($primary2, left);
      }

      .questionnaire--contacts,
      .questionnaire--socials {
        @include size(100%, auto);
        margin: 0;
        padding: 0;
        list-style-type: none;
      }

      .questionnaire--contacts {
        padding-block: 30px 16px;
        @include flex(column, start, start, 16px);

        &-item {
          a {
            text-decoration: none;
            @include p3($primary2, left);
            @include flex(row, start, center, 8px);
            transition: color 0.3s ease;

            &:hover {
              color: $primary1;
            }

            &:hover div {
              opacity: 0.5;
            }

            div {
              @include size(30px, 30px);
              border-radius: 50%;
              background-color: $primary3;
              @include flex(row, center, center, 0);
              opacity: 1;
              transition: opacity 0.3s ease;

              img {
                @include size(16px, 16px);
              }
            }
          }
        }
      }

      .questionnaire--socials {
        @include flex(row, start, center, 20px);

        a {
          opacity: 1;
          transition: opacity 0.3s ease;

          &:hover {
            opacity: 0.5;
          }

          img {
            @include size(16px, 16px);
          }
        }
      }
    }
  }

  &--bio {
    @include size(100%, auto);
    @include flex(column, start, stretch, 10px);

    &-title {
      @include h2($primary2, left);
    }

    &-text {
      @include t2($primary2, left);
    }
  }
}
</style>
