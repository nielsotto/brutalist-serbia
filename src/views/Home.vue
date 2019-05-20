<template>
  <div class="home-wrapper">
    <Hero />
  </div>
</template>

<script>
// @ is an alias to /src
import Hero from "@/components/Hero.vue";

export default {
  name: "home",
  components: {
    Hero
  }
};
</script>

<style lang="scss" scoped>
  .home-wrapper {
    
  }
</style>
