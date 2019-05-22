<template>
    <div class="buttonStack">
        <full-button :primary="true" :text="'Read History'"></full-button>
        <full-button :primary="false" :text="'See Popular Bloks'"></full-button>
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
        bottom: 0;
        width: 100%;
    }
</style>