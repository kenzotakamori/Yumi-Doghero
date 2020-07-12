<template>
    <header>
        <!-- <ul>
            <li>
                <a href="#" @click.prevent="navigate('app-home')">Home</a>
            </li>
            <li>
                <a href="#" @click.prevent="navigate('app-about')">About</a>
            </li>
            <li>
                <a href="#" @click.prevent="navigate('app-dogs')">Dogs</a>
            </li>
            <li>
                <a href="#" @click.prevent="navigate('app-calendar')">Calendar</a>
            </li>
            <li>
                <a href="#" @click.prevent="navigate('app-contact')">Contact</a>
            </li>
        </ul> -->
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
        <div class="hamburguer-menu">
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
            navigate(newView) {
                eventBus.$emit('changeView', {
                    view: newView
                })
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

    header .hamburguer-menu {
        width: 5%;
    }

    header .message {
        width: 90%;
        transition: 0.5s ease-in-out;
    }

</style>