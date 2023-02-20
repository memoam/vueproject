<template>
  <div class="middleBannersCom">
    <div
      class="middleBannersCom__img"
      v-for="bannerData in middleBanners"
      v-bind:key="bannerData.id"
    >
      <img :src="require(`@/assets/${bannerData.image}`)" alt="Banner" />
    </div>
  </div>
</template>

<script>
export default {
  name: 'MiddleBannersCom',
  props: {
    middleBanners: Array,
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.middleBannersCom {
  width: 100%;
  display: flex;
  flex-direction: column;

  &__img {
    width: 100%;
    margin-bottom: 1em;
    img {
      width: 100%;
    }
  }
}
</style>
