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
        top: 0;
        left: 0;
        z-index: 8;
        background-color: #ff3333;
        width: 50%;
        height: 100vh;
        line-height: 70px; 
    }

    .hamburguer-menu .hamburguer-option {
        padding-left: 15px;
    }

    .hamburguer-menu .hamburguer-option a{
        font-weight: 700;
        font-size: larger;
        color: #fff;
        text-decoration: none;
    }

    .hide-menu {
        visibility: hidden;
    }
</style>
