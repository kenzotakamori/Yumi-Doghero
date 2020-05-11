<template>
    <div class="app-header">
        <ul>
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
        </ul>
    </div>
</template>

<script>
    import { eventBus } from './main'

    export default {
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
    .app-header {
        background-color: red;
        height: 40px;
        line-height: 40px;
        text-align: center;
    }

    .app-header ul {
        display: flex;
        flex-direction: row;
        width: 100%;
        margin: 0;
        padding: 0;
    }

    .app-header ul li {
        list-style-type: none;
        font-weight: 700;
        width: 20%;
    }

    .app-header ul li a {
        text-decoration: none;
        color: white;
    }
</style>