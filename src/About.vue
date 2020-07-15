<template>
    <section id="app-about">
        <div class="container">
            <h1>About</h1>
        </div>
    </section>
</template>

<script>
    import { eventBus } from './main';

    export default {
        created() {
            eventBus.$emit('aboutLoaded', {
                flag: true
            })            
        }    
    }
</script>