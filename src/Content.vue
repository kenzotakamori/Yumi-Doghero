<template>
    <div id="app-content">
        <keep-alive>
            <component :is="currentView"></component>
        </keep-alive>
    </div>   
</template>

<script>
    import Home from './Home.vue';
    import About from './About.vue';
    import Dogs from './Dogs.vue';
    import Calendar from './Calendar.vue';
    import Contact from './Contact.vue';
    import { eventBus } from './main';

    export default {
        created() {
            eventBus.$on('changeView', (data) => {
                this.view = data.view
            });
        },
        data() {
            return {
                view: "app-home"
            }
        },
        computed: {
            currentView() {
                return this.view;
            }
        },
        components: {
            appHome: Home,
            appAbout: About,
            appDogs: Dogs,
            appCalendar: Calendar,
            appContact: Contact
        }
    }
</script>