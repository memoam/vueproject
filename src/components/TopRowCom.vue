<template>
  <div class="topRowCom">
    <img :src="require(`@/assets/${bannerTop}`)" alt="BannerTop" />
  </div>
</template>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.topRowCom {
  position: absolute;
  top: 0;
  img {
    width: 100%;
    min-height: 3em;
  }
}
</style>

<script>
export default {
  name: 'TopRowCom',
  props: {
    bannerTop: String,
  },
};
</script>
