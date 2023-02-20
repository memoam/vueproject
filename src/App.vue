<template>
  <header class="header" id="d">
    <div class="headerTop">
      <div class="headerTop__logo">
        <img alt="DDt logo" src="./assets/Logo.svg" />
      </div>
      <div class="headerTop__search">
        <input type="text" />
        <button type="button">
          <img src="./assets/search.svg" alt="Search" />
        </button>
      </div>
      <div class="headerTop__userData">
        <a href="#">
          <img alt="Vue logo" src="./assets/Carrito.svg" />
          <p>(0)</p>
        </a>
        <a href="#">
          <img alt="Vue logo" src="./assets/Login.svg" />
          <p>(0)</p>
        </a>
      </div>
      <div class="headerTop__socialNetworks">
        <p>fa</p>
        <p>fa</p>
        <p>fa</p>
      </div>
    </div>
    <!-- <nav>
      <router-link to="/">Home</router-link> |
      <router-link to="/about">memo es putp</router-link>
    </nav> -->
    <NavBarCom />
  </header>
  <router-view />
</template>

<style scoped lang="scss">
.header {
  position: fixed;
  width: 100%;
  margin-top: 3em;
  background: #ebebeb;
  z-index: 10;
}
.headerTop {
  width: 80%;
  margin: 0 auto;
  display: flex;
  padding: 1.5em 0;
  justify-content: space-between;
  position: relative;
  @media (max-width: 1065px) {
    width: 90%;
    padding: 3.5em 0 0.5em;
  }
  &__logo {
    display: flex;
    align-items: center;
    justify-content: center;
    @media (max-width: 1065px) {
      position: absolute;
      top: 0.5em;
      left: 0;
      right: 0;
    }
    img {
      width: 100px;
    }
  }
  &__search {
    display: flex;
    align-items: center;
    justify-content: center;
    width: 50%;
    @media (max-width: 1065px) {
      width: 100%;
    }
    button {
      border-top-left-radius: 0;
      border-bottom-left-radius: 0;
    }
    input {
      border-top-right-radius: 0;
      border-bottom-right-radius: 0;
    }
  }
  &__userData {
    display: flex;
    @media (max-width: 1065px) {
      position: absolute;
      top: 1em;
      right: 5%;
    }
    a {
      display: flex;
      align-items: center;
      justify-content: center;
      &:first-child {
        margin-right: 1.5em;
      }
    }
  }
  &__socialNetworks {
    display: flex;
    align-items: center;
    justify-content: center;
    @media (max-width: 1065px) {
      display: none;
    }
  }
}
</style>
<script>
import NavBarCom from '@/components/NavBarCom.vue';

export default {
  created() {
    window.addEventListener('scroll', this.handleScroll);
  },
  unmounted() {
    window.removeEventListener('scroll', this.handleScroll);
  },
  methods: {
    handleScroll(event) {
      if (window.scrollY > 20) {
        document.getElementById('d').style.marginTop = '0';
      } else document.getElementById('d').style.marginTop = '3em';
    },
  },
  name: 'App',
  components: {
    NavBarCom,
  },
};
</script>
