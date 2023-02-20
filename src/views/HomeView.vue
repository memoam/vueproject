<template>
  <div class="home">
    <TopRowCom v-if="windowWidth >= 768" v-bind:bannerTop="bannerTop.image" />
    <TopRowCom v-else v-bind:bannerTop="bannerTopMovil.image" />
    <CarouselCom v-bind:bannersCarousel="bannersCarousel" />
    <RowImagesCom v-bind:menuData="menuTop" />
    <div class="body">
      <div v-if="windowWidth >= 1000" class="banners">
        <MiddleBannersCom v-bind:middleBanners="middleBanners" />
      </div>
      <div class="products" v-if="windowWidth >= 700">
        <p>Productos destacados</p>
        <div
          class="products__product"
          v-for="product in products"
          v-bind:key="product.id"
        >
          <ProductsCom v-bind:product="product" />
        </div>
        <p>Productos destacados</p>
        <div
          class="products__product"
          v-for="product in products"
          v-bind:key="product.id"
        >
          <ProductsCom v-bind:product="product" />
        </div>
      </div>
      <div v-else class="productsMovile">
        <p>Productos destacados</p>
        <ProductsMovileCom v-bind:products="products" />
        <p>Productos destacados</p>
        <ProductsMovileCom v-bind:products="products" />
      </div>
    </div>

    <BottomBannerCom v-bind:bannersBottom="bannersBottom" />
    <RowImagesCom v-bind:menuData="menuBottom" />
    <NewsletterCom />
    <FooterCom msg="footer" />
  </div>
</template>

<script>
// @ is an alias to /src
import CarouselCom from '@/components/CarouselCom.vue';
import TopRowCom from '@/components/TopRowCom.vue';
import MiddleBannersCom from '@/components/MiddleBannersCom.vue';
import ProductsCom from '@/components/ProductsCom.vue';
import ProductsMovileCom from '@/components/ProductsMovileCom.vue';
import BottomBannerCom from '@/components/BottomBannerCom.vue';
import RowImagesCom from '@/components/RowImagesCom.vue';
import NewsletterCom from '@/components/NewsletterCom.vue';
import FooterCom from '@/components/FooterCom.vue';
import {
  bannerTop,
  middleBanners,
  bannersBottom,
  bannersCarousel,
  bannerTopMovil,
} from '@/helpers/BannersHelp.js';
import { menuTop, menuBottom } from '@/helpers/MenuHelp.js';
import { products } from '@/helpers/ProductsHelp.js';

export default {
  name: 'HomeView',
  components: {
    CarouselCom,
    TopRowCom,
    MiddleBannersCom,
    ProductsCom,
    ProductsMovileCom,
    BottomBannerCom,
    RowImagesCom,
    NewsletterCom,
    FooterCom,
  },
  data() {
    return {
      windowWidth: window.innerWidth,
      bannerTop,
      bannerTopMovil,
      bannersCarousel,
      middleBanners,
      menuTop,
      products,
      bannersBottom,
      menuBottom,
    };
  },

  mounted() {
    this.$nextTick(() => {
      window.addEventListener('resize', this.onResize);
    });
  },
  beforeDestroy() {
    window.removeEventListener('resize', this.onResize);
  },
  methods: {
    onResize() {
      this.windowWidth = window.innerWidth;
    },
  },
};
</script>
<style scoped lang="scss">
.home {
  padding-top: 11.8em;
  margin: 0;
  font-family: Montserrat;
  overflow-x: hidden;

  @media (max-width: 1065px) {
    padding-top: 10em;
  }
  @media (max-width: 400px) {
    font-size: 0.9em;
  }
}
.body {
  width: 80%;
  margin: 0 auto;
  display: flex;
  justify-content: space-between;
  @media (max-width: 768px) {
    width: 90%;
  }
  @media (max-width: 400px) {
    width: 100%;
  }
}
.banners {
  margin-top: 2.5em;
  width: 20%;
}
.productsMovile {
  width: 100%;
  margin-bottom: 5em;
  p {
    width: 100%;
    margin: 1.5em 0 0.5em;
    text-transform: uppercase;
    font-size: 1em;
    font-weight: bold;
    text-align: center;
  }
}
.products {
  display: flex;
  align-items: flex-start;
  justify-content: space-between;
  flex-wrap: wrap;
  width: 75%;
  margin-bottom: 5em;
  @media (max-width: 1000px) {
    width: 100%;
  }
  p {
    width: 100%;
    margin: 1.5em 0 0.5em;
    text-transform: uppercase;
    font-size: 2em;
    font-weight: bold;
    text-align: center;
  }
  &__product {
    width: 30%;
  }
}
</style>
