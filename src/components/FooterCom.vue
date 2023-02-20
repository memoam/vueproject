<template>
  <footer class="footer">
    <div class="footer__main">
      <div class="footer__body">
        <div class="footer__menu">
          <div class="footer__submenu">
            <a href=""></a>
            <p class="footer__submenu_title">Menu</p>
            <a href="" class="footer__submenu_a">Productos</a>
            <a href="" class="footer__submenu_a">Tiendas</a>
            <a href="" class="footer__submenu_a">Configurar pc</a>
            <a href="" class="footer__submenu_a">¿Que juegas?</a>
            <a href="" class="footer__submenu_a">Pride</a>
            <a href="" class="footer__submenu_a">Nosotros</a>
          </div>
          <div class="footer__submenu">
            <p class="footer__submenu_title">informacion</p>
            <a href="" class="footer__submenu_a">Productos</a>
            <a href="" class="footer__submenu_a">Tiendas</a>
            <a href="" class="footer__submenu_a">Configurar pc</a>
            <a href="" class="footer__submenu_a">¿Que juegas?</a>
            <a href="" class="footer__submenu_a">Pride</a>
            <a href="" class="footer__submenu_a">Nosotros</a>
          </div>
        </div>
        <div class="footer__socialNetworks">
          <img
            class="footer__socialNetworks_logo"
            src="@/assets/LogoFooter.svg"
            alt="LogoFooter"
          />
          <div class="footer__socialNetworks_social">
            <a href="">
              <img src="@/assets/fb.svg" alt="fb" />
            </a>
            <a href="">
              <img src="@/assets/yt.svg" alt="yt" />
            </a>
            <a href="">
              <img src="@/assets/tw.svg" alt="tw" />
            </a>
            <a href="">
              <img src="@/assets/in.svg" alt="in" />
            </a>
          </div>
        </div>
        <div class="footer__payments">
          <p>METODOS DE PAGO</p>
          <div class="footer__payments_logos">
            <img src="@/assets/pp.svg" alt="pp" />
            <img src="@/assets/ppp.svg" alt="ppp" />
            <img src="@/assets/ps.svg" alt="ps" />
            <img src="@/assets/mp.svg" alt="mp" />
            <img src="@/assets/pv.svg" alt="pv" />
            <img src="@/assets/mc.svg" alt="mp" />
          </div>
        </div>
      </div>
      <p class="footer__copyright">copyright</p>
    </div>
  </footer>
</template>

<script>
export default {
  name: 'FooterCom',
  props: {
    msg: String,
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.footer {
  width: 100%;
  background: #0057b8;
  &__main {
    padding: 2em 0;
    width: 80%;
    margin: 0 auto;
    display: flex;
    align-items: center;
    justify-content: center;
    flex-direction: column;
    @media (max-width: 900px) {
      width: 90%;
    }
  }
  &__body {
    display: flex;
    align-items: center;
    justify-content: center;
    width: 100%;
    padding: 1em 0 2em;
    border-bottom: 1px solid #73a2d6;
    @media (max-width: 900px) {
      flex-direction: column;
    }
  }
  &__copyright {
    padding: 2em 0 0;
    color: #fff;
  }
  &__menu,
  &__socialNetworks,
  &__payments {
    display: flex;
    width: 33.33%;
    align-items: center;
    justify-content: center;
    padding: 1em 0;
    border-right: 1px solid #73a2d6;
    min-height: 216px;
    @media (max-width: 900px) {
      width: 100%;
      border-right: none;
    }
  }
  &__menu {
    align-items: flex-start;
    justify-content: flex-start;
    @media (max-width: 900px) {
      align-items: center;
      justify-content: center;
    }
  }
  &__submenu {
    margin-right: 2em;
    display: flex;
    flex-direction: column;
    &_a {
      color: #fff;
      font-size: 14px;
      font-weight: 300;
      margin-bottom: 0.5em;
    }
    &_title {
      font-size: 15px;
      font-weight: bold;
      text-transform: uppercase;
      color: #fff;
      margin-bottom: 1em;
    }
  }
  &__socialNetworks {
    flex-direction: column;
    &_logo {
      width: 50%;
    }
    &_social {
      display: flex;
      align-items: center;
      justify-content: center;
      margin-top: 3em;
      img {
        width: 30px;
        margin: 0 1em;
      }
    }
  }
  &__payments {
    flex-direction: column;
    border: none;
    p {
      font-size: 16px;
      font-weight: bold;
      text-transform: uppercase;
      color: #fff;
      margin-bottom: 1em;
    }
    &_logos {
      display: flex;
      align-items: center;
      justify-content: center;
      flex-wrap: wrap;
      img {
        width: 100px;
      }
    }
  }
}
</style>
