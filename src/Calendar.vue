<template>
    <section id="app-calendar">
        <div class="container">
            <h1>Calendar</h1>
        </div>
    </section>
</template>

<script>
    import { eventBus } from './main';

    export default {
        created() {
            eventBus.$emit('calendarLoaded', true)            
        }    
    }
</script>