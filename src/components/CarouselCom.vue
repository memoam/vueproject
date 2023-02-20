<template>
  <Splide :options="options" aria-label="My Favorite Images" id="splide">
    <SplideSlide
      v-for="bannerData in bannersCarousel"
      v-bind:key="bannerData.id"
      class="page"
    >
      <img :src="require(`@/assets/${bannerData.image}`)" alt="Banner" />
      <div class="page__data">
        <p class="page__data_title">{{ bannerData.title }}</p>
        <p class="page__data_info">{{ bannerData.info }}</p>
        <p class="page__data_lastPrice">{{ bannerData.lastPrice }}</p>
        <p class="page__data_newPrice">{{ bannerData.newPrice }}</p>
        <button class="page__data_btn">VER PRODUCTO</button>
      </div>
    </SplideSlide>
  </Splide>
</template>
<style scoped lang="scss">
.page {
  position: relative;
  width: 100%;

  &__data {
    position: absolute;
    top: 15%;
    right: 10%;
    width: 300px;
    @media (max-width: 500px) {
      width: 100px;
      top: 2%;
    }
    &_newPrice,
    &_title {
      font-size: 2.5em;
      font-weight: bold;
      text-transform: uppercase;
      @media (max-width: 500px) {
        font-size: 0.9em;
      }
    }
    &_info {
      font-size: 0.7em;
      margin: 1em 0;
      color: #c8c8c8;
      font-weight: 200;
      @media (max-width: 500px) {
        font-size: 7px;
      }
    }
    &_lastPrice {
      font-size: 1.5em;
      color: #c8c8c8;
      font-weight: 200;
      @media (max-width: 500px) {
        font-size: 10px;
      }
    }
    &_btn {
      border-radius: 10px;
      float: right;
      margin-top: 1em;
      @media (max-width: 500px) {
        font-size: 12px;
      }
    }
    p {
      color: white;
      text-align: right;
    }
  }
  img {
    width: 100%;
  }
}
</style>

<script>
import '@splidejs/vue-splide/css';
import '@splidejs/vue-splide/css/core';
import { Splide, SplideSlide } from '@splidejs/vue-splide';
import { defineComponent } from 'vue';

export default defineComponent({
  name: 'CarouselCom',
  props: {
    bannersCarousel: Array,
  },
  components: {
    Splide,
    SplideSlide,
  },
  data() {
    const options = {
      rewind: true,
      gap: '1em',
      arrows: false,
      drag: true,
      autoplay: true,
      interval: 5000,
      pagination: true,
    };

    return { options };
  },
});
</script>
