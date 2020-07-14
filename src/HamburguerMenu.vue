<template>
  <div class="hamburguer-menu" :class="[showMenu ? '' : 'hide-menu']" v-click-outside="hide">
      <div v-for="option in hamburguerOptions" :key="option.title" class="hamburguer-option">
          <a @click.prevent="navigate(option.section)">
              {{option.title}}
          </a>
      </div>
  </div>
</template>

<script>
    import ClickOutside from 'vue-click-outside'
    import { eventBus } from './main';

    export default {
        created () {
            eventBus.$on('openMenu', () => {
                this.showMenu = true;
            });
        },
        data () {
            return {
                showMenu: false,
                hamburguerOptions: [
                    {
                        title: 'Home',
                        section: 'app-home'
                    },
                    {
                        title: 'Sobre',
                        section: 'app-about'
                    },
                    {
                        title: 'Dogs',
                        section: 'app-dogs'
                    },
                    {
                        title: 'Agenda',
                        section: 'app-calendar'
                    },
                    {
                        title: 'Contato',
                        section: 'app-contact'
                    },
                ]
            }
        },
        methods: {
            navigate(newView) {
                eventBus.$emit('changeView', {
                    view: newView
                });
                this.showMenu = false;
            },
            hide() {
                console.log('tentando esconder!')
                if (this.showMenu) {
                    this.showMenu = false;
                }
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
        -webkit-box-shadow: 0 5px 5px -3px rgba(0,0,0,.2), 0 8px 10px 1px rgba(0,0,0,.14), 0 3px 14px 2px rgba(0,0,0,.12);
        box-shadow: 0 5px 5px -3px rgba(0,0,0,.2), 0 8px 10px 1px rgba(0,0,0,.14), 0 3px 14px 2px rgba(0,0,0,.12);
    }

    .hide-menu {
        visibility: hidden;
    }
</style>
