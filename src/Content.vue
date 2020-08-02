<template>
    <div id="app-content">
        <app-cover></app-cover>
        <app-home v-if="coverLoaded"></app-home>
        <app-about v-if="homeLoaded"></app-about>
        <app-dogs v-if="aboutLoaded"></app-dogs>
        <app-calendar v-if="dogsLoaded"></app-calendar>
        <app-contact v-if="calendarLoaded"></app-contact>        
    </div>   
</template>

<script>
    import Cover from './Cover.vue';
    import Home from './Home.vue';
    import About from './About.vue';
    import Dogs from './Dogs.vue';
    import Calendar from './Calendar.vue';
    import Contact from './Contact.vue';
    import { eventBus } from './main';

    export default {
        created() {
            eventBus.$on('coverLoaded', (data) => {
                this.coverLoaded = true
            });
            eventBus.$on('homeLoaded', (data) => {
                this.homeLoaded = true
            });
            eventBus.$on('aboutLoaded', (data) => {
                this.aboutLoaded = true
            });
            eventBus.$on('dogsLoaded', (data) => {
                this.dogsLoaded = true
            });
            eventBus.$on('calendarLoaded', (data) => {
                this.calendarLoaded = true
            });
        },
        data() {
            return {
                view: "app-cover",
                coverLoaded: false,
                homeLoaded: false,
                aboutLoaded: false,
                dogsLoaded: false,
                calendarLoaded: false
            }
        },
        computed: {
            currentView() {
                return this.view;
            }
        },
        components: {
            appCover: Cover,
            appHome: Home,
            appAbout: About,
            appDogs: Dogs,
            appCalendar: Calendar,
            appContact: Contact
        }
    }
</script>
<style>
    .container {
        display: grid;
        place-items: center;
        max-width: 1140px!important;
        min-height: 80vh;
        padding-right: 10px;
        padding-left: 20px;
        padding-top: 60px;
        margin-right: auto;
        margin-left: auto;
    }

    h1 {
        position: sticky;
        top: 50px;
        padding-left: 20px;
        line-height: 80px;
        background-image: linear-gradient(rgba(255,255,255,1) 40%, rgba(255,255,255,0) 100%);
    }    
</style>