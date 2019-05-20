<template>
    <div id="mobile-menu" :class="{ menuOpen: menuIsOpen }">
        <div class="menu-links-wrapper">
            <router-link v-for="link in links" :key="link.id" :to="link.routeUrl" :class="{menuOpen: menuIsOpen}">
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
        left: auto;
        z-index: 665;
        width: 0;
        transition: all .5s ease-out;
        padding: 0;

        a {
            color: $primaryColor;
        }

        h3 {
            margin-top: 2rem;
        }

        .menu-links-wrapper {
            bottom: 0;
            position: fixed;
            margin-bottom: 2rem;
        }

        &.menuOpen {
            width: 100%;
            padding: 20px;
        }
    }

</style>