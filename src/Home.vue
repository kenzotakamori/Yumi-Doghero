<template>
    <section id="app-home">
        <h1>Home</h1>
        <div class="carousel-container">
            <div class="home-resources-content">
                <div class="row">
                    <div id="carousel-home-resources" class="carousel-home-resources">
                        <carousel-3d 
                                    :perspective="30"
                                    :border="0"
                                    :width="585"
                                    :height="370"
                                    :controls-visible="true"
                                    :space="500"
                                    :clickable="true">
                            <slide v-for="(image, index) in carouselImages" :key="index" :index="index">
                                <img :src="image.imgSrc">
                            </slide>
                        </carousel-3d>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>

<script>
    import carouselImages from './assets/carousel_mock'
    import { Carousel3d, Slide } from 'vue-carousel-3d';
    import { eventBus } from './main';

    export default {
        components: {
            Carousel3d,
            Slide
        },
        created() {
            eventBus.$emit('homeLoaded', true);            
        },
        data() {
            return {
                carouselImages: carouselImages,
                slideIndex: 1,
                slides: 3
            }
        }
    }
</script>
<style>
    .carousel-container {
        width: 100%;
        height: 100vh;
        padding-top: 60px;
    }
    .carousel-container  h1 {
        padding-left: 30px;
    }
    .carousel-home-resources .left-1 {
        transform: translateX(-500px) translateZ(-400px) rotateY(-30deg) !important;
    }
    .carousel-home-resources .right-1 {
        transform: translateX(500px) translateZ(-400px) rotateY(30deg) !important;
    }
</style>