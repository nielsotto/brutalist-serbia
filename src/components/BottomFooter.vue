<template>
    <footer>
        <p>{{text}}</p>
    </footer>
</template>

<script>
    export default {
        name: "BottomFooter",
        props: ['text']
    }
</script>

<style lang="scss" scoped>
@import "../assets/style/vars.scss";

footer {
    background: $primaryColor;
    height: 90px;
    padding: 0 20px;
    display: flex;
    align-items: center;
    margin-top: 80px;
    margin-bottom: 0;
    margin-left: -$navMargin;
    margin-right: -$navMargin;

    p {
        margin: 0;
        color: $primaryLight;
    }
}

</style>