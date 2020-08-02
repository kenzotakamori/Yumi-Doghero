<template>
    <div class="hamburguer-window">
        <div class="hamburguer-background" @click="hide">
            <transition name="slide" appear>
                <div class="hamburguer-menu shadowing" v-if="openMenu">
                    <div v-for="option in hamburguerOptions" :key="option.title" class="hamburguer-option">
                        <a :href="option.section">
                            {{option.title}}
                        </a>
                    </div>
                </div>
            </transition>
        </div>
    </div>
</template>

<script>
    import { eventBus } from './main';

    export default {
        data () {
            return {
                openMenu: true,
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
                this.openMenu = false;
                let timeout = setTimeout(() => {
                    eventBus.$emit('showMenu', false);
                }, 200);
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

    .hamburguer-menu .hamburguer-option:hover {
        background-color: #bb2c2c;
    }

    .hamburguer-menu .hamburguer-option a{
        font-weight: 700;
        font-size: larger;
        color: #fff;
        text-decoration: none;
        display: inline-block;     
        position: relative;    
        width: 100%;
        padding-left: 15px;
    }

    .hamburguer-menu .hamburguer-option a:hover{
        color: #909090;
    }

    .hide-menu {
        visibility: hidden;
    }

    .slide-enter, .slide-leave-to {
        transform: translateX(-100%);
    }

    .slide-enter-to, .slide-leave {
        transform: translateX(0);
    }

    .slide-enter-active {
        transition: transform .3s;
    }

    .slide-leave-active {
        transition: transform .2s;
    }
</style>
