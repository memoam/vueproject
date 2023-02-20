<template>
  <div class="navTop">
    <div class="nav">
      <input type="checkbox" id="nav-check" />
      <div class="nav-btn">
        <label for="nav-check">
          <span></span>
          <span></span>
          <span></span>
        </label>
      </div>

      <div class="nav-links">
        <p>Categorias</p>
        <a href="">Tiendas</a>
        <a class="blue" href="">configurar tu pc</a>
        <a class="blue" href="">¿que juegas?</a>
        <a class="blue" href="">pride</a>
        <a href="">Nosotros</a>
        <a href="">Blog</a>
        <a href="">Contacto</a>
        <a href="">ayuda</a>
      </div>
    </div>
  </div>
</template>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.navTop {
  width: 100%;
  background-color: #1d1d1d;
  position: relative;
  // @media (max-width: 900px) {
  //   margin-top: -3.2em;
  // }
}
// .nav {
//   height: 50px;
//   width: 100%;
//   margin: 0 auto;
// }

// .nav > .nav-header {
//   display: inline;
// }

// .nav > .nav-header > .nav-title {
//   display: inline-block;
//   font-size: 16px;
//   color: #f5f5f5;
//   padding: 10px 10px 10px 10px;
// }

.nav > .nav-btn {
  display: none;
}

.nav > .nav-links {
  display: flex;
  align-items: center;
  justify-content: center;
  // font-size: 16px;
}
.blue {
  color: #efefef;
  background: #0057b8;
}
.nav > .nav-links > a {
  display: inline-block;
  padding: 0.7em 1em;
  text-decoration: none;
  color: #efefef;
  text-transform: uppercase;
}

.nav > .nav-links > a:hover {
  background-color: rgba(0, 0, 0, 0.3);
}

.nav > #nav-check {
  display: none;
}

@media (max-width: 1065px) {
  .nav > .nav-btn {
    display: inline-block;
    position: absolute;
    left: 3%;
    top: -7em;
  }
  .nav > .nav-btn > label {
    display: inline-block;
    width: 50px;
    height: 50px;
    padding: 13px;
    cursor: pointer;
  }
  .nav > .nav-btn > label:hover,
  .nav #nav-check:checked ~ .nav-btn > label {
    background-color: rgba(0, 0, 0, 0.1);
  }
  .nav > .nav-btn > label > span {
    display: block;
    width: 25px;
    height: 10px;
    border-top: 3px solid #707070;
  }
  .nav > .nav-links {
    position: absolute;
    display: block;
    width: 100%;
    background-color: #333;
    height: 0px;
    transition: all 0.3s ease-in;
    overflow-y: hidden;
    top: 50px;
    left: 0px;
  }
  .nav > .nav-links > a {
    display: block;
    width: 100%;
  }
  .nav > #nav-check:not(:checked) ~ .nav-links {
    height: 0px;
  }
  .nav > #nav-check:checked ~ .nav-links {
    height: calc(100vh - 50px);
    overflow-y: auto;
    margin-top: -3.2em;
  }
}
</style>
