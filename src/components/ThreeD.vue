<template>
    <div class="three-dee">
        <h4> {{ text }}</h4>
        <div class="three-canvas">

        </div>
        <p>Rotate with your finger</p>

    </div>
</template>

<script>
    export default {
        name: 'ThreeD',
        props: ['text'],
        
    }
</script>

<style lang="scss" scoped>
.three-canvas {
    height: 335px;
}

p {
    text-align: center;
}

h4 {
    margin: 0;
}

</style>