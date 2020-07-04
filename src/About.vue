<template>
    <div class="app-about">
        <h1>About</h1>
    </div>
</template>

<script>
    import { eventBus } from './main';

    export default {
        created() {
            eventBus.$emit('aboutLoaded', true)            
        }    
    }
</script>