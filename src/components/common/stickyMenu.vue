<template>
  <div class="sticky-menu sticky-shadow">
    <a href="#">
      <i class="fa-solid fa-ruler-combined"></i>
    </a>
    <a href="">
      <i class="fa-solid fa-life-ring"></i>
    </a>
    <a href="#">
      <i class="fa-solid fa-book"></i>
    </a>
    <a href="#">
      <i class="fa-solid fa-cart-shopping"></i>
    </a>
  </div>
</template>

<script>

  export default {
    name:'stickyMenu',
  }

</script>

<style lang="scss" scoped>

  @import "@/styles/general.scss";

  .sticky-menu {
    @extend .t-align-c;
    position: fixed;
    top: 25vh;
    right: 0;
    padding: 1.3rem 0.8rem 0.7rem;
    background-color: $median_hint_of_red;
    border-top-left-radius: 10px;
    border-bottom-left-radius: 10px;


    a {
      display: block;
      padding-bottom: 0.6rem;
      font-size: 1.3rem;
      color: $dark_color;
      text-shadow: 0 0 1px $material_corduray;

      &:hover {
        @extend .standard-hover;
        text-shadow: 2px 1px 1px $cube_port_gore;
      }
    }
  }

</style>