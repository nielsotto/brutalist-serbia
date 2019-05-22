<template>
<div id="mobile-presentation-container">
  <div id="app">
    <nav-bar @toggleMenuIsOpen="toggleMenuIsOpen"></nav-bar>
    <mobile-menu :menuIsOpen="menuIsOpen"></mobile-menu>
    <!-- <div id="nav">
      <router-link to="/">Home</router-link> |
      <router-link to="/about">About</router-link>
    </div> -->
    <router-view />
    <bottom-footer :text="'© Visit Serbia'"></bottom-footer>
  </div>
</div>
</template>

<script>
import NavBar from '@/components/NavBar';
import MobileMenu from '@/components/MobileMenu';
import BottomFooter from '@/components/BottomFooter';

export default {
  components: {
    NavBar,
    MobileMenu,
    BottomFooter
  },
  data() {
    return {
      menuIsOpen: false
    }
  },
  methods: {
    toggleMenuIsOpen() {
      console.log('her')
      this.menuIsOpen = !this.menuIsOpen;
    }
  },
  watch: {
    $route(){
      this.menuIsOpen = false;
    }
  },
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

#mobile-presentation-container {
  max-height: 375px;
  max-width: 812px;
}

a {
  text-decoration: none;
}

#app {
  padding: 0;
  margin: $navHeight 20px 0 20px;
}

/* footer {
  height: 90px;
  background: $primaryColor;
} */
</style>
