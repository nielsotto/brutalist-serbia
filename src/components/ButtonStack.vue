<template>
    <div class="buttonStack">
        <full-button :bgColor="'#2BFCDC'" :textColor="'#802CD7'" :text="'Read History'"></full-button>
        <full-button :bgColor="'#802CD7'" :textColor="'#FEE4DD'" :text="'See Popular Bloks'"></full-button>
    </div>
</template>

<script>
import FullButton from '@/components/FullButton';
    export default {
        name: "ButtonStack",
        components: {
            FullButton
        },
    }
</script>

<style lang="scss" scoped>
@import "../assets/style/vars.scss";
    .buttonStack {
        position: absolute;
        bottom: $navHeight;
        width: 100%;
    }
</style>