<template>
    <nav>
        <router-link to="/">
            <div id="logo">
                <h5>BLOK</h5>
            </div>
        </router-link>

        <div id="menu-btn" @click="menuIsOpen = !menuIsOpen">
            <!-- <div class="inner"></div> -->
        </div>
        
    </nav>
</template>

<script>
    export default {
        name: "NavBar",
        data: function(){
            return {
                menuIsOpen: false
            }
        }/* ,
        methods: {
            openMenu(){
                this.$emit('openMenu');
                this.menuIsOpen = !this.menuIsOpen;
            }
        } */
    }
</script>

<style lang="scss" scoped>
@import "../assets/style/type.scss";

$menuSize: 35px;
$navMargin: 20px;
    nav {
        height: $navHeight;
        display: flex;
        align-items: center;
        justify-content: space-between;
        position: fixed;
        top: 0;
        left: $navMargin;
        right: $navMargin;
        z-index: 666;

        a {
            color: $primaryColor;
        }

        h5 {
            margin: 0;
        }

        #menu-btn {
            width: $menuSize;
            height: $menuSize;
            border: 2px solid $primaryColor;
            background: $accentColor;
            transition: all .2s ease-out;

            /* &.open {
                width: 100%;
                width: 100%;

                .inner {
                    opacity: 1;
                }
            }

            .inner {
                opacity: 0;
                width: 100%;
                height: 100%;
                transition: all .2s ease-out;
            } */
        }
    }
</style>