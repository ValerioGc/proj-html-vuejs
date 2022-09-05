<template>
  <li>
    <a :href="navL[idx].link" class="navLName">
      {{navL[idx].name}}
      <i class="fa-solid fa-angle-down"></i>
    </a>
  </li>
</template>

<script>

  export default {
    name:'navItems',
    props: {
      navL: Array,
      idx: Number,
    }
  }

</script>

<style lang="scss">

  @import "../styles/vars.scss";
  @import "../styles/general.scss";

  .navLName {
    @extend .cubeWhiteColor;
    padding-right: 3px ;
  }

</style>