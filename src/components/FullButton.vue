<template>
    <!-- <a class="full-button" :style="{ backgroundColor: bgColor, color: textColor }"> -->
        <router-link :to="'/brutalism'" class="full-button" :style="{ backgroundColor: bgColor, color: textColor }">
            <h5>
                {{ text }}
            </h5>
        </router-link>
    <!-- </a> -->
</template>

<script>
    export default {
        name: "FullButton",
        props: ['text', 'primary'],
        computed: {
            textColor() {
                return this.primary ? '#802CD7' : '#FEE4DD';
            },
            bgColor() {
                return this.primary ? '#2BFCDC' : '#802CD7';
            }
        },
    }
</script>

<style lang="scss" scoped>
@import '../assets/style/vars.scss';

.full-button{
    width: 100%;
    height: $navHeight;
    padding: 0 20px;
    display: flex;
    align-items: center;

    h5 {
        margin: 0;
    }
}

</style>