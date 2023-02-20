<template>
  <div class="rowImagesCom">
    <div class="rowImagesCom__body">
      <div
        class="rowImagesCom__img"
        v-for="data in menuData"
        v-bind:key="data.id"
      >
        <img
          class="rowImagesCom__img_svg"
          v-if="data.image.endsWith('svg')"
          :src="require(`@/assets/${data.image}`)"
          alt="Banner"
        />
        <img
          class="rowImagesCom__img_jpg"
          v-else
          :src="require(`@/assets/${data.image}`)"
          alt="Banner"
        />
        <p>{{ data.text }}</p>
        <p v-if="data.textTwo !== '' || data.textTwo !== undefined">
          {{ data.textTwo }}
        </p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'RowImagesCom',
  props: {
    menuData: Array,
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.rowImagesCom {
  width: 100%;
  background: #1c1c1c;
  &__body {
    display: flex;
    align-items: center;
    justify-content: center;
    flex-wrap: wrap;
    width: 80%;
    margin: 0 auto;
    padding: 3em 0 2em;
    @media (max-width: 768px) {
      width: 90%;
    }
  }
  &__img {
    width: 25%;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    @media (max-width: 825px) {
      width: 50%;
    }
    // max-height:100px ;
    &_svg {
      width: 30%;
      padding: 0.3em 0.3em 1em;
    }
    &_jpg {
      width: 50%;
      padding-bottom: 1em;
    }
    p {
      color: #fff;
      @media (max-width: 768px) {
        font-size: 12px;
      }
    }
  }
}
</style>
