<template>
  <div class="hero">
    <!-- <h1>{{ msg }}</h1> -->
    <h1 v-for="headline in headlines" :key="headline.id">
      {{ headline.message }}
    </h1>
  </div>
</template>

<script>
export default {
  name: "Hero",
  props: {
    
  },
  data: function() {
    return {
      headlines: [
        {
          id: 1,
          message: "Welcome Welcome Welcome"
        },
        {
          id: 2,
          message: "Serbia Serbia Serbia"
        },
        {
          id: 3,
          message: "Yas Yas Yas"
        },
        {
          id: 4,
          message: "Maybe Maybe Maybe"
        }
      ]
    }
      
  }
  
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss" scoped>
@import '@/assets/style/vars.scss';

  .hero {
    margin: 0 -20px;
    overflow: hidden;

    h1 {
      white-space: nowrap;
    }
  }
</style>
