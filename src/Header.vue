<template>
    <header>
        <div class="logo">
            Y
        </div>
        <div class="message">
            <template v-if="isCoverVisible">
                Vai viajar? 
            </template>
            <template v-else>
                Deixe seu dog comigo!
            </template>
        </div>
        <div class="menu-button" @click.stop="openMenu">
            H
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
        background-color: red;
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
        color: white;
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