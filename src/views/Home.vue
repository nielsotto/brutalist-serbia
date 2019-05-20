<template>
  <div class="home-wrapper">
    <Hero />
    <side-scroll :text="'Yo!'"></side-scroll>
  </div>
</template>

<script>
// @ is an alias to /src
import Hero from "@/components/Hero.vue";
import SideScroll from "@/components/SideScroll.vue";

export default {
  name: "home",
  components: {
    Hero,
    SideScroll
  }
};
</script>

<style lang="scss" scoped>
  .home-wrapper {
    
  }
</style>
