<template>
    <div class="app-about">
        This is about page
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