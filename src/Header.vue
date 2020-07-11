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
        <div v-if="isCoverVisible" class="message">
            Vai viajar? Deixe seu dog comigo!
        </div>
        <div v-else>
            Testando
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
        height: 10vh;
        line-height: 40px;
        text-align: center;
        position: fixed;
        top: 0;
        left: 0;
        display: flex;
        flex-direction: row;
    }

    header ul {
        display: flex;
        flex-direction: row;
        width: 100%;
        margin: 0;
        padding: 0;
    }

    header ul li {
        list-style-type: none;
        font-weight: 700;
        width: 20%;
    }

    header ul li a {
        text-decoration: none;
        color: white;
    }
</style>