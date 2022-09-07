<template>
  <li class="navL-container">
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

<style lang="scss" scoped>

  @import "@/styles/general.scss";

  .navLName {
    @extend .cubeWhiteColor;
    margin-right: 1rem ;
    padding-right: 5px;

    &:hover {
      @extend .standard-hover;
    }
    &:hover .navL-container{
      transform: translateY(50px);
    }
  }

</style>