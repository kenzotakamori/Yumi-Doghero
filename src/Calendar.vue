<template>
    <div id="app-calendar">
        This is Calendar page
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