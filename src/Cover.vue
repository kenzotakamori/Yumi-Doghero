<template>
    <section class="app-cover" v-observe-visibility="coverVisibilityChanged">
        <div class="initial">
            cover
        </div>
    </section>
</template>

<script>
    import { eventBus } from './main';
    import { ObserveVisibility } from "vue-observe-visibility";

    export default {
        directives: {
            ObserveVisibility
        },
        created() {
            eventBus.$emit('coverLoaded', true);            
        },
        methods: {
            coverVisibilityChanged: function(isVisible, entry) {
                eventBus.$emit('coverVisibilityChanged', isVisible)
            }
        } 
    }
</script>
<style>
    .app-cover {
        width: 100%;
        height: 100vh;
        text-align: center;
        background-color: red;
        display: flex;
        -webkit-box-shadow: 0 5px 5px -3px rgba(0,0,0,.2), 0 8px 10px 1px rgba(0,0,0,.14), 0 3px 14px 2px rgba(0,0,0,.12);
        box-shadow: 0 5px 5px -3px rgba(0,0,0,.2), 0 8px 10px 1px rgba(0,0,0,.14), 0 3px 14px 2px rgba(0,0,0,.12);
    }
    .initial {
        margin: 100px;
    }
</style>