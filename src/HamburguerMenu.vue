<template>
  <div class="hamburguer-menu shadowing" v-click-outside="hide">
      <div v-for="option in hamburguerOptions" :key="option.title" class="hamburguer-option">
          <a :href="option.section" @click="hide">
              {{option.title}}
          </a>
      </div>
  </div>
</template>

<script>
    import ClickOutside from 'vue-click-outside'
    import { eventBus } from './main';

    export default {
        data () {
            return {
                hamburguerOptions: [
                    {
                        title: 'Home',
                        section: '#app-home'
                    },
                    {
                        title: 'Sobre',
                        section: '#app-about'
                    },
                    {
                        title: 'Dogs',
                        section: '#app-dogs'
                    },
                    {
                        title: 'Agenda',
                        section: '#app-calendar'
                    },
                    {
                        title: 'Contato',
                        section: '#app-contact'
                    },
                ]
            }
        },
        methods: {
            hide() {
                eventBus.$emit('showMenu', false);
            }
        },
        directives: {
            ClickOutside
        }
    }
</script>

<style>
    .hamburguer-menu {
        position: fixed;
        display: inline-block;
        top: 50px;
        right: 5px;
        z-index: 8;
        background-color: #fff;
        width: 100px;
        line-height: 40px; 
    }

    .hamburguer-menu .hamburguer-option {
        padding-left: 5px;
    }

    .hamburguer-menu .hamburguer-option a{
        color: #000000;
        text-decoration: none;
    }

    .hide-menu {
        visibility: hidden;
    }
</style>
