<template>
    <section class="app-cover shadowing" v-observe-visibility="isCoverVisible">
        <div class="initial">
            cover
        </div>
    </section>
</template>

<script>
    import { eventBus } from './main';
    import { ObserveVisibility } from 'vue-observe-visibility';

    export default {
        directives: {
            ObserveVisibility
        },
        created() {
            eventBus.$emit('coverLoaded', true);            
        },
        methods: {
            isCoverVisible: function(isVisible, entry) {
                eventBus.$emit('isCoverVisible', isVisible)
            }
        } 
    }
</script>
<style>
    .app-cover {
        width: 100%;
        height: 100vh;
        text-align: center;
        background-color: #ff3333;
        display: flex;
    }
    .initial {
        margin: 100px;
    }
</style>