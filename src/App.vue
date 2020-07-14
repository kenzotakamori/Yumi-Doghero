<template>
  <div id="app">
    <hamburguer-menu></hamburguer-menu>
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

  export default {
    name: 'app',
    data () {
      return {
      msg: 'Welcome to Your Vue.js App'
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
  body {
    margin: 0;
    width: 100%;
  }
</style>
