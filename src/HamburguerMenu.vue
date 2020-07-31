<template>
    <div class="hamburguer-window">
        <transition name="background">
            <div class="hamburguer-background" @click="hide">
                <transition>
                    <div class="hamburguer-menu shadowing">
                        <div v-for="option in hamburguerOptions" :key="option.title" class="hamburguer-option">
                            <a :href="option.section" @click="hide">
                                {{option.title}}
                            </a>
                        </div>
                    </div>
                </transition>
            </div>
        </transition>
    </div>
</template>

<script>
    import { eventBus } from './main';

    export default {
        data () {
            return {
                hamburguerOptions: [
                    {
                        title: 'Home',
                        section: '#app-home'
                    },
                    {
                        title: 'Sobre',
                        section: '#app-about'
                    },
                    {
                        title: 'Dogs',
                        section: '#app-dogs'
                    },
                    {
                        title: 'Agenda',
                        section: '#app-calendar'
                    },
                    {
                        title: 'Contato',
                        section: '#app-contact'
                    },
                ]
            }
        },
        methods: {
            hide() {
                eventBus.$emit('showMenu', false);
            }
        }
    }
</script>

<style>
    .hamburguer-background {
        position: fixed;
        width: 100%;
        height: 100%;
        z-index: 7;
        background-color: rgba(0,0,0,.5);
        opacity: 1;
    }

    .hamburguer-menu {
        position: fixed;
        display: inline-block;
        top: 0;
        left: 0;
        z-index: 8;
        background-color: #ff3333;
        width: 50%;
        height: 100vh;
        line-height: 70px; 
    }

    .hamburguer-menu .hamburguer-option {
        padding-left: 15px;
    }

    .hamburguer-menu .hamburguer-option a{
        font-weight: 700;
        font-size: larger;
        color: #fff;
        text-decoration: none;
        display: inline-block;     
        position: relative;    
        width: 100%;
    }

    .hide-menu {
        visibility: hidden;
    }
</style>
