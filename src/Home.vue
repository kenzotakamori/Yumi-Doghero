<template>
    <section class="app-home">
        <div class="container">
            <h1>Home</h1>
        </div>
    </section>
</template>

<script>
    import { eventBus } from './main';

    export default {
        created() {
            eventBus.$emit('homeLoaded', true)            
        }    
    }
</script>