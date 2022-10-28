<template>
  <header>
    <nav class="container">
      <router-link to="/">
        <img src="../assets/wdev.svg" alt="WDEC" id="logo" />
      </router-link>
        <img src="../assets/menu.svg" alt="Open-menu" id="menu" @click="openMenu" />
      <div id="overlay-menu" v-if="menuActive" @click="closeMenu"></div>
      <div id="menu-items" :class="{active:menuActive}">
        <img src="../assets/wdev.svg" alt="WDEC" id="logo-menu" />
        <ul>
          <li @click="closeMenu"><router-link to="/">Home</router-link></li>
          <li @click="closeMenu"><router-link to="/videos">Vídeos</router-link></li>
          <li @click="closeMenu"><router-link to="/sobre">Sobre</router-link></li>
          <li @click="closeMenu"><router-link to="/contato">Contato</router-link></li>
        </ul>
      </div>
    </nav>
  </header>
</template>

<script>
export default {
    name: "Navbar-v",
    data () {
      return {
        menuActive: false,
      }
    },
    methods:{
      openMenu: function () {
        this.menuActive = true;
      },
      closeMenu: function () {
        this.menuActive = false;
      }
    }
}
</script>

<style scoped>
header {
    width: 100%;
    height: 60px;
    background-color: var(--color-background-nav);
    display: flex;
    justify-content: center;
    align-items: center;
  }

nav{
  display: flex;
  justify-content: space-between;
  height: 60px;
  align-items: center;
}

#logo {
    width: 130px;
  }

#menu {
  width: 30px;
}

#overlay-menu {
  width: 40%;
  height: 100%;
  position: fixed;
  left: 0; top: 0;
  background-color: rgba(0,0,0,0.8);
}

#logo-menu {
  width: 110px;
  margin: 20px 0 10px 0;
}

#menu-items {
  position: fixed;
  display: none;
  align-items: center;
  justify-content: flex-start;
  flex-direction: column;
  right: 0; top: 0;
  width: 60%;
  height: 100%;
  background-color: var(--color-background-nav);
}

#menu-items.active {
    display: flex;
}

ul {
  list-style: none;
  text-align: center;
}

ul li {
  margin: 20px 0 20px 0;
}

ul li a {
  color: var(--color-text-light);
}

@media (min-width: 750px) {
  #menu-items,
  #logo-menu,
  #overlay-menu, #menu{
    display: none;
  }
  #menu-items {
    display: flex;
    position: static;
    height: 60px;
    width: auto;
  }
  ul{
    display: flex;
    height: 60px;
  align-items: center;

  }
  ul li {
    margin: 0 20px 0 0;
  }
}
</style>