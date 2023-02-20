<template>
  <div class="productsCom">
    <p class="productsCom__product_exists" v-if="product.exists">
      EN EXISTENCIA
    </p>
    <p class="productsCom__product_noexists" v-else>SIN EXISTENCIA</p>
    <p class="productsCom__product_offer" v-if="product.offer">¡OFERTA!</p>
    <a href="#">
      <img
        class="productsCom__product_productImg"
        :src="require(`@/assets/${product.image}`)"
        alt="BannerTop"
      />
      <p class="productsCom__product_title">{{ product.title }}</p>
      <p class="productsCom__product_description">{{ product.description }}</p>
    </a>
    <div class="productsCom__product_prices">
      <p class="productsCom__product_previousprice" v-if="product.offer">
        {{ product.previousprice }}
      </p>
      <p class="productsCom__product_price">{{ product.price }}</p>
      <button><img src="@/assets/addCart.svg" alt="addCart" /></button>
    </div>
  </div>
</template>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.productsCom {
  position: relative;
  margin-top: 3em;
  &__product {
    &_productImg {
      width: 100%;
      margin-left: 2em;
    }
    &_offer,
    &_noexists,
    &_exists {
      position: absolute;
      background: #1d73c6;
      padding: 0.3em 0.7em;
      border-top-right-radius: 5px;
      border-bottom-right-radius: 5px;
      color: #fff;
      top: 0;
      left: 0;
    }
    &_noexists {
      background: #b7b7b7;
    }
    &_offer {
      top: 2.5em;
      background: #fe0000;
    }
    &_title {
      padding-left: 3em;
      text-align: center;
      font-size: 18px;
      font-weight: bold;
      margin-bottom: 0.5em;
      @media (max-width: 400px) {
        padding: 1em;
      }
    }
    &_description {
      padding-left: 2em;
      text-align: center;
      font-size: 14px;
      @media (max-width: 400px) {
        padding: 1em;
      }
    }
    &_prices {
      padding-left: 2.5em;
      position: relative;
      display: flex;
      justify-content: space-between;
      align-items: center;
      margin-top: 2.3em;
      @media (max-width: 400px) {
        justify-content: space-around;
        padding: 1em;
      }
      button {
        padding: 0.3em;
        padding-bottom: 0;
        border-radius: 5px;
        img {
          margin: 0;
          width: 28px;
        }
      }
    }
    &_previousprice {
      position: absolute;
      text-decoration: line-through;
      color: #b7b7b7;
      font-weight: 200;
      bottom: 2em;
      @media (max-width: 400px) {
        bottom: 3em;
        left: 4.3em;
      }
    }
    &_price {
      color: #0057b8;
      font-size: 22px;
    }
  }
}
</style>

<script>
export default {
  name: 'ProductsCom',
  props: {
    product: Object,
  },
};
</script>
