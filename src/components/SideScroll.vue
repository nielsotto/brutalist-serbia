<template>
    <div class="sideScroll">
        <h4> {{ text }}</h4>
    </div>
</template>

<script>
    export default {
        name: 'SideScroll',
        props: ['text']
    }
</script>

<style lang="scss" scoped>
    .sideScroll {
        position: relative;
        height: 500px;
    }

    h4 {
        margin-top: 0;
    }
</style>