<template>
    <div id="mobile-menu" :class="{ menuOpen: menuIsOpen }">
        <div class="menu-links-wrapper">
            <router-link v-for="link in links" :key="link.id" :to="link.routeUrl">
                <h3>
                    {{ link.headline }}
                </h3>
            </router-link>
        </div>
    </div>
</template>

<script>
    import NavBar from '@/components/NavBar';
    export default {
        name: "MobileMenu",
        components: {
            NavBar
        },
        props: ['menuIsOpen'],
        /* methods: {
            openMenu(){
                this.$emit('openMenu');
            }
        }, */
        data: function(){
            return {
                links: [
                    {
                        id: 1,
                        headline: 'Front Page',
                        routeUrl: '/'
                    },
                    {
                        id: 2,
                        headline: 'Buildings',
                        routeUrl: '/buildings'
                    },
                    {
                        id: 3,
                        headline: 'Brutalism',
                        routeUrl: '/brutalism'
                    },
                    {
                        id: 4,
                        headline: 'Neo Belgrade',
                        routeUrl: '/neo-belgrade'
                    }
                ]
            }
        },
    }
</script>

<style lang="scss" scoped>
@import "../assets/style/vars.scss";

    #mobile-menu {
        height: 100vh;
        background: $accentColor;
        position: fixed;
        top: 0;
        right: 0;
        transform: translateX(100%);
        left: auto;
        z-index: 665;
        transition: all .5s ease-out;
        padding: 0;

        a {
            color: $primaryColor;

            h3 {
                margin: 2rem 0;
            }

            &.router-link-exact-active {
                color: $primaryLight;
            }
        }

        .menu-links-wrapper {
            position: absolute;
            left: $navMargin;
            right: $navMargin;
            bottom: 0;
        }

        &.menuOpen {
            width: 100vw;
            padding: $navMargin;
            transform: translateX(0);
        }
    }

</style>