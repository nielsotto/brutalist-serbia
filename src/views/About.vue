<template>
  <div class="about">
    <div class="brutal-hero"></div>
    <div class="brutal-gradient"></div>
    <h2>Society</h2>
    <h3>And other great things</h3>
    <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo.</p>
    <h4>Here we see greatness</h4>
    <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo.</p>
  </div>
</template>

<style lang="scss" scoped>
@import '../assets/style/vars.scss';

  h2 {
    -webkit-text-fill-color: transparent;
    -webkit-text-stroke: .02em $primaryColor;
    margin-top: -$navHeight;
    position: absolute;
  }

  h3 {
    margin: 0;
    margin-bottom: 1em;
  }

  .brutal-hero {
    margin-top: -$navHeight;
    margin-left: -$navMargin;
    margin-right: -$navMargin;
    //width: 100%;
    height: 65vh;
    background: $accentColor;
    background-image: url('../assets/images/buildings/b1.jpg');
    background-position: center center;
    background-repeat: no-repeat;
    background-attachment: fixed;
    background-size: cover;
  }

  .brutal-gradient {
    background-image: linear-gradient(to bottom, rgba($primaryLight, 0) 0%, rgba($primaryLight, 1) 100%);
    height: 65vh;
    width: 100vw;
    position: absolute;
    top: 0;
    left: 0;
  }

</style>

