<template>
    <header :class="{shadowing: !isCoverVisible}">
        <div class="menu-button" @click.stop="openMenu" @mouseover="openMenu">
            <i class="fa fa-bars"></i>
        </div>
        <div class="message">
            <transition mode="out-in">
                <span v-if="isCoverVisible" key="cover-visible">Vai viajar?</span>
                <span v-else key="cover-invisible">Deixe seu dog comigo!</span>
            </transition>
        </div>
        <div class="logo">
            Y
        </div>
    </header>
</template>

<script>
    import { eventBus } from './main'

    export default {
        created() {
            eventBus.$on('coverVisibilityChanged', (flag) => {
                this.isCoverVisible = flag;
            });
        },
        data() {
            return {
                isCoverVisible: true
            }
        },
        methods: {
            openMenu() {
                eventBus.$emit('showMenu', true);
            }
        }
        
    }
</script>

<style>
    header {
        background-color: #ff3333;
        width: 100%;
        z-index: 2;
        height: 50px;
        line-height: 50px;
        text-align: center;
        position: fixed;
        top: 0;
        left: 0;
        display: flex;
        flex-direction: row;
    }

    header div {
        display: inline;
        margin: 0;
        padding: 0;
        font-weight: 700;
        color: #fff;
        text-align: center;
    }

    header .logo {
        width: 5%;
    }

    header .menu-button {
        width: 5%;
    }

    header .message {
        width: 90%;
        transition: 0.5s ease-in-out;
    }

    @media(min-width: 768px) {
        /* Configurações desktop */
        /* header {
            background-color: blue;
        } */
    }
</style>