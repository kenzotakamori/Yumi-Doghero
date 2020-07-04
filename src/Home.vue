<template>
    <div class="app-home">
        <h1>Home</h1>
    </div>
</template>

<script>
    import { eventBus } from './main';

    export default {
        created() {
            eventBus.$emit('homeLoaded', true)            
        }    
    }
</script>