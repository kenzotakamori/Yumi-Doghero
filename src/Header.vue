<template>
    <header :class="{shadowing: !isCoverVisible}">
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
        <div class="menu-button" @click.stop="openMenu" @mouseover="openMenu">
            <svg xmlns="http://www.w3.org/2000/svg" width="20" height="14" viewBox="0 0 20 14">
                <g fill="none" fill-rule="evenodd" stroke="#FFF" stroke-linecap="round" stroke-linejoin="round" stroke-width="2">
                    <path d="M1 7h18M1 1h18M1 13h18"/>
                </g>
            </svg>
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