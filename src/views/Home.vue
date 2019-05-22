<template>
  <div class="home-wrapper">
    <Hero />
    <side-scroll :text="'Popular Buildings'"></side-scroll>
    <three-d :text="'Explore from Home'"></three-d>
  </div>
</template>

<script>
// @ is an alias to /src
import Hero from "@/components/Hero.vue";
import SideScroll from "@/components/SideScroll.vue";
import ThreeD from "@/components/ThreeD.vue";

export default {
  name: "home",
  components: {
    Hero,
    SideScroll,
    ThreeD
  }
};
</script>

<style lang="scss" scoped>

  
</style>
