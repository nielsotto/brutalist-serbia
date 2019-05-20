<template>
    <a class="full-button" :style="{ backgroundColor: bgColor, color: textColor }">
            <h5>
                {{ text }}
            </h5>
    </a>
</template>

<script>
    export default {
        name: "FullButton",
        data: function(){
            return{
                
            }
        },
        props: ['bgColor', 'textColor', 'text']
        /* {
            button: {
                primary: {
                    background: '#2BFCDC',
                    color: '#802CD7',
                    },
                secondary: {
                    background: '#802CD7',
                    color: '#FEE4DD',
                }
            }
        } */
    }
</script>

<style lang="scss" scoped>
@import '../assets/style/vars.scss';

.full-button{
    width: 100%;
    height: 90px;
    padding: 0 20px;
    display: flex;
    align-items: center;

    h5 {
        margin: 0;
    }
}

</style>