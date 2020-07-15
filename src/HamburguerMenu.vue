<template>
  <div class="hamburguer-menu" v-click-outside="hide">
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
        top: 10px;
        right: 5px;
        z-index: 8;
        background-color: #fff;
        width: 100px;
        line-height: 40px; 
        -webkit-box-shadow: 0 5px 5px -3px rgba(0,0,0,.2), 0 8px 10px 1px rgba(0,0,0,.14), 0 3px 14px 2px rgba(0,0,0,.12);
        box-shadow: 0 5px 5px -3px rgba(0,0,0,.2), 0 8px 10px 1px rgba(0,0,0,.14), 0 3px 14px 2px rgba(0,0,0,.12);
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
