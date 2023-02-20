<template>
  <div class="bottomBannerCom">
    <div
      class="bottomBannerCom__img"
      v-for="bannerData in bannersBottom"
      v-bind:key="bannerData.id"
    >
      <img :src="require(`@/assets/${bannerData.image}`)" alt="Banner" />
    </div>
  </div>
</template>

<script>
// import { bannersBottom } from '@/helpers/BannersHelp.js';

export default {
  name: 'BottomBannerCom',
  props: {
    bannersBottom: Array,
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.bottomBannerCom {
  width: 100%;
  display: flex;
  align-items: center;
  justify-content: center;
  flex-wrap: wrap;
  &__img {
    width: 50%;
    margin-bottom: -5px;
    @media (max-width: 768px) {
      width: 100%;
    }
    img {
      width: 100%;
    }
  }
}
</style>
