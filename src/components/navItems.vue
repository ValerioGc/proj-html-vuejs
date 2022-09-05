<template>
  <li>
    <a :href="navL[idx].path" class="navLName">
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
    margin-right: 1rem ;
    padding-right: 4px;

    &:hover:not(i) {
      color: $cube_mountain_meadow;
    }
  }

</style>