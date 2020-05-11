<template>
    <div id="app-dogs">
        This is Dogs page
    </div>
</template>

<script>
    import dogs from '/assets/dogs_mock.js'
    import { eventBus } from './main';

    export default {
        created() {
            eventBus.$emit('dogsLoaded', true)            
        }    
    }
</script>