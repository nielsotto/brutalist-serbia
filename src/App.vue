<template>
  <div id="app">
    <nav-bar></nav-bar>
    <mobile-menu></mobile-menu>
    <!-- <div id="nav">
      <router-link to="/">Home</router-link> |
      <router-link to="/about">About</router-link>
    </div> -->
    <router-view />
  </div>
</template>

<script>
import NavBar from '@/components/NavBar';
import MobileMenu from '@/components/MobileMenu';
export default {
  components: {
    NavBar,
    MobileMenu
  },
  data: {
    menuIsOpen: false
  }
}
</script>


<style lang="scss">
@import "./assets/style/type.scss";

* {
  box-sizing: border-box;
}

body, html {
  margin: 0;
  padding: 0;
}

body {
  //overflow-x: hidden;
  background: $primaryLight;
}

a {
  text-decoration: none;
}

#app {
  padding: 0;
  margin: $navHeight 20px;
}
</style>
