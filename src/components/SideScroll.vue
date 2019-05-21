<template>
    <div class="sideScroll">
        <h4> {{ text }}</h4>
        <div class="scrolling-wrapper">
            <div class="cards" v-for="image in images" :key="image.id">
                <img :src="image.src" :alt="image.alt">
                <p>{{image.title}}</p>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        name: 'SideScroll',
        props: ['text'],
        data: () => {
            return {
                images: [
                    {
                        id: 1,
                        title: 'Evil Looking',
                        // Kopieret fra sidebaren
                        // src/assets/images/buildings/b1.jpg
                        // src: '../assets/images/buildings/b1.jpg',
                        // "../assets/style/vars.scss"
                        src: 'https://upload.wikimedia.org/wikipedia/commons/a/aa/Jugotours_Beograd_Dec_2003.jpg',
                        alt: 'A great building'
                    },
                    {
                        id: 2,
                        title: 'Evil Looking',
                        //src: '../assets/images/buildings/fox.jpg',
                        src: 'http://2.bp.blogspot.com/-HVds66TUkcY/Uq4lFRANTQI/AAAAAAAAE84/N2_utb5Exxc/s1600/800px-Forum_Krako%CC%81w_10-2003.jpg',
                        alt: 'A great building'
                    },
                    {
                        id: 3,
                        title: 'Evil Looking',
                        //src: './assets/images/buildings/b3.jpg',
                        src: 'http://jrrny.com/wp-content/uploads/journeys/divokoza/ca0b13e3717c4b967c4c33aef4326637.jpg',
                        alt: 'A great building'
                    },
                ]
            }
        }
    }
</script>

<style lang="scss" scoped>
@import "../assets/style/vars.scss";

    .sideScroll {
        position: relative;
        margin-bottom: 72px;

        .scrolling-wrapper {
            overflow-x: scroll;
            overflow-y: hidden;
            white-space: nowrap;
            -webkit-overflow-scrolling: touch;
            &::-webkit-scrollbar {
                display: none;
            }

            .cards {
                display: inline-block;
                height: 370px;
                max-width: 250px;
                overflow: hidden;
                margin-right: 20px;
                position: relative;
                &:last-child{
                    margin-right: 0;
                }

                img {
                    height: 100%;
                    display: block;
                    margin-left: 0;
                    margin-right: 0;
                }

                p {
                    position: absolute;
                    bottom: 8px;
                    left: 16px;
                    margin: 0;
                    color: $accentColor;
                }
            }
        }
    }

    h4 {
        margin-top: 0;
    }
</style>