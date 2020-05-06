<template>
    <div id="app-header">
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