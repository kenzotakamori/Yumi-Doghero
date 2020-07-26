<template>
    <section id="app-dogs">
        <div class="container">
            <h1>Dogs</h1>
            <table>
                <tr>
                    <td class="dogs-catalog">
                        <div v-for="dog in dogs" :key="dog.id">
                            <img class="shadowing" :src="dog.imgUrl" @click="showSelectedDog(dog)">
                        </div>
                    </td>
                    <td class="dogs-info">
                        <template v-if="selectedDog" class="dog-picture">
                            <img class="shadowing" :src="selectedDog.imgUrl">
                            <h2>{{selectedDog.name}}</h2>
                            <p>{{selectedDog.comment}}</p>
                        </template>
                        <template v-else>
                            <p>Clique em algum dog!</p>   
                        </template>
                    </td>
                </tr>
            </table>
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
    #app-dogs table{
        width: 100%;
        grid-template-columns: 2fr 1fr;
    }

    #app-dogs table td{
        width: 100%;
    }

    .dogs-catalog {
       display: grid;
       grid-template-columns: repeat(4, 1fr);
       height: 300px;
       overflow-y: scroll;
    }

    .dogs-catalog img{
        max-height: 70px;
        margin: 10px;
        border-radius: 5px 20px 5px;
        border: 1px solid red;
    }

    .dogs-info img {
        max-height: 300px;
        border-radius: 150px;
        border: 1px solid red;
    }
</style>