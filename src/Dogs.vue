<template>
    <section id="app-dogs">
        <h1>Dogs</h1>
        <div class="container">
            <div class="dogs-section">
                <div class="dogs-info">
                    <transition name="pulse" mode="out-in">
                        <div class="selected-dog" v-if="selectedDog" :key="selectedDog.id">
                            <img class="shadowing" :src="selectedDog.imgUrl">
                            <h2>{{selectedDog.name}}</h2>
                            <span>{{selectedDog.comment}}</span>
                        </div>
                        <p v-else>Clique em algum dog!</p>   
                    </transition>
                </div>
                <div class="dogs-catalog">
                    <div v-for="dog in dogs" :key="dog.id">
                        <img class="shadowing" :src="dog.imgUrl" @click="showSelectedDog(dog)">
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>

<script>
    import dogs from './assets/dogs_mock'
    import { eventBus } from './main';

    export default {
        created() {
            eventBus.$emit('dogsLoaded', true);
        },
        data() {
            return{
                dogs: dogs,
                selectedDog: null
            }
        },
        methods: {
            showSelectedDog: function(dog) {
                this.selectedDog = dog;
            }
        }
    }
</script>

<style>
    .dogs-section{
        width: 100%;
        max-height: 80vh;
        display: grid;
        grid-template-columns: minmax(250px, 30%) 1fr;
    }

    .dogs-section .dogs-catalog {
        display: grid;
        grid-gap: 0.5rem;
        grid-template-columns: repeat(auto-fill, minmax(70px, 1fr));
        height: 70vh;
        overflow-y: scroll;
    }

    .dogs-section .dogs-catalog img{
        max-width: 70px;
        border-radius: 5px 20px 5px;
        border: 1px solid #ff3333;
    }

    .dogs-section .dogs-info {
        display: grid;
        place-items: center;
        height: 100%;
    }

    .dogs-section .dogs-info div.selected-dog {
        display: grid;
        place-items: center;
    }

    .dogs-section .dogs-info img {
        max-width: 90%;
        border-radius: 150px;
        border: 1px solid #ff3333;
    }

    .dogs-section .dogs-info span {
        text-align: center;
    }

    .pulse-enter-active {
        animation: bounce-in .5s;
    }

    .pulse-leave{
        opacity: 1;
    }

    .pulse-leave-to {
        opacity: 0;
    }

    .pulse-leave-active {
        transition: opacity .3s;
    }

    @keyframes bounce-in {
        0% {
            opacity: .5;
            transform: scale(0);
        }
        50% {
            opacity: 0.7;
            transform: scale(1.1);
        }
        100% {
            opacity: 1;
            transform: scale(1);
        }
    }
</style>