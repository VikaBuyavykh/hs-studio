<script setup>
const pricing = [
  {
    title: 'Design advices',
    price: '29',
    points: [
      'General living space advices',
      'Rennovation advices',
      'Interior design advices',
      'Furniture reorganization',
      'Up to 5 hours meetings',
    ],
  },
  {
    title: 'Complete interior',
    price: '39',
    points: [
      'Complete home redesign',
      'Interior and exterior works',
      'Modular interior planning',
      'Kitchen design',
      'Garages organization',
    ],
  },
  {
    title: 'Furniture design',
    price: '59',
    points: [
      'Furniture for living room',
      'Furniture refurbishment',
      'Sofas and amchairs',
      'Tables and chairs',
      'Kitchens',
    ],
  },
]
</script>

<template>
  <section class="pricing" id="pricing">
    <div class="pricing--content">
      <h2 class="pricing--title">Тарифы</h2>
      <ul class="pricing--cards">
        <li v-for="item in pricing" :key="item.title" class="pricing--card">
          <div class="pricing--card-overlay"></div>
          <div class="pricing--card-box">
            <h3 class="pricing--card-title">{{ item.title }}</h3>
            <p class="pricing--card-price">
              $ <span>{{ item.price }}</span
              >/month
            </p>
            <span class="pricing--line"></span>
            <ul class="pricing--card-list">
              <li v-for="(point, index) in item.points" :key="index" class="pricing--card-point">
                {{ point }}
              </li>
            </ul>
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

.pricing {
  @include size(100%, auto);
  padding-block: 60px;

  &--content {
    @extend %sizing;
    @include flex(column, center, stretch, 48px);
  }

  &--title {
    @include h2($primary2, center);
  }

  &--cards {
    margin: 0;
    padding: 0;
    @include size(100%, auto);
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    grid-template-rows: 1fr;
    gap: 36px;
    list-style-type: none;
  }

  &--card {
    background-color: $primary3;
    position: relative;

    &:first-of-type .pricing--card-overlay {
      background-image: url('/back1.jpg');
    }

    &:nth-of-type(2) .pricing--card-overlay {
      background-image: url('/back2.jpg');
    }

    &:nth-of-type(3) .pricing--card-overlay {
      background-image: url('/back3.jpg');
    }

    &-overlay {
      position: absolute;
      @include size(100%, 100%);
      opacity: 0.5;
      @extend %bgi;
    }

    &-box {
      position: relative;
      margin: 100px 20px;
      @include flex(column, start, stretch, 10px);
    }

    &-title {
      @include p1($primary2, center);
      font-weight: bold;
    }

    &-price {
      @include t1($primary2, center);

      span {
        @include h2($primary2, center);
      }
    }

    .pricing--line {
      @include size(75%, 1px);
      margin-inline: auto;
      margin-bottom: 16px;
      background-color: $primary2;
    }

    &-list {
      margin: 0;
      padding: 0;
      list-style-type: disc;
      @include flex(column, start, center, 10px);
    }

    &-point {
      @include t1($primary2, center);
    }
  }
}
</style>
