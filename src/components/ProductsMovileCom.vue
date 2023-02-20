<template>
  <Splide :options="options" aria-label="My Favorite Images" id="splide">
    <SplideSlide
      v-for="product in products"
      v-bind:key="product.id"
      class="page"
    >
      <ProductsCom v-bind:product="product" />
    </SplideSlide>
  </Splide>
</template>
<style scoped lang="scss">
.page {
  width: 100%;
}
</style>

<script>
import '@splidejs/vue-splide/css';
import '@splidejs/vue-splide/css/core';
import ProductsCom from '@/components/ProductsCom.vue';

import { Splide, SplideSlide } from '@splidejs/vue-splide';
import { defineComponent } from 'vue';

export default defineComponent({
  name: 'ProductsMovileCom',
  props: {
    products: Array,
  },
  components: {
    ProductsCom,
    Splide,
    SplideSlide,
  },
  data() {
    const options = {
      rewind: true,
      gap: '1em',
      arrows: true,
      drag: true,
      autoplay: false,
      pagination: false,
    };

    return { options };
  },
});
</script>
