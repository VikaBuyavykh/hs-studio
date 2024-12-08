<script setup>
import { team } from '@/utils/team'
</script>

<template>
  <section class="team" id="team">
    <div class="team--content">
      <h2 class="team--title">Команда</h2>
      <ul class="team--list">
        <li v-for="item in team" :key="item.id">
          <RouterLink :to="{ name: 'team', params: { id: item.id } }" class="team--item">
            <div class="team--photo-box">
              <img class="team--photo" :src="item.image" :alt="item.name" />
              <div class="team--overlay">
                <img class="team--quotes" src="/quotes.svg" alt="Кавычки" />
                <blockquote>{{ item.blockquote }}</blockquote>
                <cite>© {{ item.cite }}</cite>
              </div>
            </div>
            <p class="team--name">{{ item.name }}</p>
            <span class="team--occupation">{{ item.occupation }}</span>
          </RouterLink>
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

.team {
  @include size(100%, auto);

  &--content {
    @extend %sizing;
    padding-block: 60px;
    @include flex(column, start, stretch, 24px);
  }

  &--title {
    @include h2($primary2, left);
  }

  &--list {
    @include size(100%, auto);
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    grid-template-rows: 1fr;
    gap: 36px;
    margin: 0;
    padding: 0;
    list-style-type: none;

    li {
      @include size(100%, auto);

      &:first-of-type .team--photo-box {
        border-top-right-radius: 100px;
      }

      &:nth-of-type(2) .team--photo-box {
        border-top-left-radius: 100px;
        border-bottom-right-radius: 100px;
      }

      &:nth-of-type(3) .team--photo-box {
        border-bottom-left-radius: 100px;
      }
    }
  }

  &--item {
    @include size(100%, auto);
    @include flex(column, start, stretch, 0);
    text-decoration: none;

    &:hover .team--photo-box .team--overlay {
      opacity: 1;
    }

    .team--photo-box {
      @include size(100%, 350px);
      position: relative;
      overflow: hidden;

      .team--photo {
        position: absolute;
        @include size(100%, 100%);
        @extend %pic;
      }

      .team--overlay {
        position: absolute;
        @include size(100%, 100%);
        @include flex(column, end, stretch, 0);
        background-image: linear-gradient(rgba($primary2, 0), rgba($primary2, 0.8));
        opacity: 0;
        transition: opacity 0.5s ease;

        img {
          @include size(16px, 16px);
          margin: 0 auto 12px 10%;
        }

        blockquote,
        cite {
          @include size(75%, auto);
          @include t2(white, left);
          margin: 0 auto;
        }

        cite {
          font-style: italic;
          text-align: end;
          margin: 8px auto 24px;
        }
      }
    }

    .team--name {
      @include p2($primary2, center);
      margin-top: 12px;
      font-weight: bold;
    }

    .team--occupation {
      @include t1($primary2, center);
    }
  }
}
</style>
