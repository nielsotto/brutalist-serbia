<template>
  <div class="hero">
    <!-- <h1>{{ msg }}</h1> -->
    <h1 v-for="headline in headlines" :key="headline.id">
      {{ headline.message }}
    </h1>
    <button-stack></button-stack>
  </div>
</template>

<script>
import ButtonStack from '@/components/ButtonStack';

export default {
  name: "Hero",
  components: {
    ButtonStack
  },
  props: {
    
  },
  data: function() {
    return {
      headlines: [
        {
          id: 1,
          message: "Genex Tower Genex Tower Genex Tower"
        },
        {
          id: 2,
          message: "SIV 3 SIV 3 SIV 3"
        },
        {
          id: 3,
          message: "Sava Centar Sava Centar Sava Centar"
        },
        {
          id: 4,
          message: "Hotel Jugoslavija Hotel Jugoslavija Hotel Jugoslavija"
        }
      ]
    }
      
  }
  
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss" scoped>
@import "../assets/style/vars.scss";

  .hero {
    margin: 0 -20px;
    overflow: hidden;
    position: relative;
    height: calc(100vh - #{$navHeight});

    h1 {
      white-space: nowrap;
    }
  }
</style>
