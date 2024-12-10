<script setup>
const projects = [
  {
    id: '01',
    theme: 'Design advices',
    title: 'Minimal Look Bedrooms',
    text: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Aliquamsem vitae turpis dignissim maximus. Aliquam sollicitudin tellumassa, vbel maximus purus posuere in. Dojrices gravida dignissim. Praesent at nibh in mi fringilla mattis. Phasellus ut  dolor odio. Aenean in the ipsum vel lectus bibendum commodo.',
    img: '/after.png',
  },
  {
    id: '02',
    theme: 'Complete interior',
    title: 'Use of Interior',
    text: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Aliquamsem vitae turpis dignissim maximus. Aliquam sollicitudin tellumassa, vbel maximus purus posuere in. Dojrices gravida dignissim. Praesent at nibh in mi fringilla mattis. Phasellus ut  dolor odio. Aenean in the ipsum vel lectus bibendum commodo.',
    img: '/Form.jpg',
  },
  {
    id: '03',
    theme: 'Furniture design',
    title: 'Make An Art',
    text: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Aliquamsem vitae turpis dignissim maximus. Aliquam sollicitudin tellumassa, vbel maximus purus posuere in. Dojrices gravida dignissim. Praesent at nibh in mi fringilla mattis. Phasellus ut  dolor odio. Aenean in the ipsum vel lectus bibendum commodo.',
    img: '/Banner.jpg',
  },
]
</script>

<template>
  <section class="projects" id="projects">
    <div class="projects--content">
      <h2 class="projects--title">Проекты</h2>
      <ul class="projects--cards">
        <li v-for="item in projects" :key="item.id" class="projects--card">
          <div class="projects--card-infobox">
            <span class="projects--number">{{ item.id }}</span>
            <div class="projects--info">
              <div class="projects--info-theme">
                <span></span>
                <p>{{ item.theme }}</p>
              </div>
              <h3 class="projects--info-title">{{ item.theme }}</h3>
              <p class="projects--info-text">{{ item.text }}</p>
              <a href="#" class="projects--info-link">Read more →</a>
            </div>
          </div>
          <div class="projects--card-img">
            <img :src="item.img" alt="Фото интерьера" class="projects--img" />
          </div>
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

.projects {
  @include size(100%, auto);
  padding-block: 60px;
  background-color: $primary3;

  &--content {
    @extend %sizing;
    @include flex(column, start, stretch, 48px);
  }

  &--title {
    @include h2($primary2, right);
  }

  &--cards {
    @include size(100%, auto);
    margin: 0;
    padding: 0;
    display: grid;
    grid-template-columns: 1fr;
    grid-template-rows: repeat(3, 1fr);
    gap: 120px;
    list-style-type: none;
  }

  &--card {
    @include size(100%, auto);
    @include flex(row, space-between, stretch, 48px);

    &:nth-of-type(2) .projects--card-infobox {
      order: 2;
    }

    &-infobox {
      @include size(60%, auto);
      position: relative;
      @include flex(column, center, center, 0);

      .projects--number {
        position: absolute;
        top: 0;
        left: 0;
        @include number(rgba($primary4, 0.2), left);
      }

      .projects--info {
        position: relative;
        @include size(90%, 65%);
        @include flex(column, start, start, 24px);

        &-theme {
          @include size(100%, auto);
          @include flex(row, start, center, 10px);

          span {
            @include size(10%, 1px);
            background-color: $primary4;
          }

          p {
            @include p2($primary4, left);
          }
        }

        &-title {
          @include h2($primary2, left);
        }

        &-text {
          @include t2($primary2, left);
        }

        &-link {
          @include t2($primary4, left);
          text-decoration: none;
          opacity: 1;
          transition: opacity 0.3s ease;

          &:hover {
            opacity: 0.5;
          }
        }
      }
    }

    .projects--card-img {
      @include size(40%, 500px);
      position: relative;

      img {
        position: absolute;
        @include size(100%, 100%);
        @extend %pic;
      }
    }
  }
}
</style>
