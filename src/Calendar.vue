<template>
    <section id="app-calendar">
        <div class="container">
            <h1>Calendar</h1>
            <calendar></calendar>
        </div>
    </section>
</template>

<script>
    import { eventBus } from './main';
    import Calendar from 'v-calendar/lib/components/calendar.umd'

    export default {
        created() {
            eventBus.$emit('calendarLoaded', true)            
        },
        components: {
            Calendar
        }    
    }
</script>