<template>
  <div id="app">
    <app-header></app-header>
    <app-content></app-content>
    <app-footer></app-footer>
  </div>
</template>

<script>
  import Header from './Header.vue';
  import Content from './Content.vue';
  import Footer from './Footer.vue';

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
      appFooter: Footer
    }
  }
</script>

<style>

</style>
