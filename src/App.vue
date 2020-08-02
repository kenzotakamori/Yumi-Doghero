<template>
  <div id="app">
    <hamburguer-menu v-if="showMenu"></hamburguer-menu>
    <app-header></app-header>
    <app-content></app-content>
    <app-footer></app-footer>
  </div>
</template>

<script>
  import Header from './Header.vue';
  import Content from './Content.vue';
  import Footer from './Footer.vue';
  import HamburguerMenu from './HamburguerMenu.vue';
  import { eventBus } from './main';

  export default {
    name: 'app',
    created () {
      eventBus.$on('showMenu', (flag) => {
        this.showMenu = flag;
      });
    },
    data () {
      return {
        showMenu: false
      }
    },
    components: {
      appHeader: Header,
      appContent: Content,
      appFooter: Footer,
      hamburguerMenu: HamburguerMenu
    }
  }
</script>

<style>
  html {
    scroll-behavior: smooth;
  }
  
  body {
    margin: 0;
    width: 100%;
    font-family: 'Proxima Nova Soft', 'Helvetica Neue', sans-serif;
  }

  .shadowing {
    -webkit-box-shadow: 0 5px 5px -3px rgba(0,0,0,.2), 0 8px 10px 1px rgba(0,0,0,.14), 0 3px 14px 2px rgba(0,0,0,.12);
    box-shadow: 0 5px 5px -3px rgba(0,0,0,.2), 0 8px 10px 1px rgba(0,0,0,.14), 0 3px 14px 2px rgba(0,0,0,.12);
  }
</style>
