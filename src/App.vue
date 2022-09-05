<template>
  <div id="app">
    <appHeader :cartItems="addedCart"/>
    <appMain />
    <appFooter />
  </div>
</template>

<script>
  import appHeader from './components/appHeader.vue';
  import appMain from './components/appMain.vue';
  import appFooter from './components/appFooter.vue';

  export default {
    name: 'App',
    components: {
      appHeader,
      appMain,
      appFooter,
    },
    data() {
      return {
        addedCart: 0,
      }
    }
  }
</script>

<style lang="scss">

  @import "./styles/vars.scss";
  @import "./styles/general.scss";

</style>
