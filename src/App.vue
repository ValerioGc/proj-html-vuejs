<template>
  <div id="app">
    <appHeader :cartItems="addedCart"/>
    <appMain />
    <appFooter />
    <stickyMenu />
    <stickyGoTop />
  </div>
</template>

<script>

// Components
  import appHeader from './components/appHeader.vue';
  import appMain from './components/appMain.vue';
  import appFooter from './components/appFooter.vue';
  import stickyMenu from "@/components/common/stickyMenu.vue";
  import stickyGoTop from "@/components/common/stickyGoTop.vue";

  export default {
    name: 'App',
    components: {
      appHeader,
      appMain,
      appFooter,
      stickyMenu,
      stickyGoTop,
    },
    data() {
      return {
        addedCart: 0,
      }
    }
  }

</script>

<style lang="scss"> @import "@/styles/general.scss"; </style>
