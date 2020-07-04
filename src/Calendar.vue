<template>
    <div id="app-calendar">
        <h1>Calendar</h1>
    </div>
</template>

<script>
    import { eventBus } from './main';

    export default {
        created() {
            eventBus.$emit('calendarLoaded', true)            
        }    
    }
</script>