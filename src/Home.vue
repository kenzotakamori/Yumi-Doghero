<template>
    <div class="app-home">
        This is home
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