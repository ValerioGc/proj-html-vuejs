<template>
  <div class="goTop sticky-shadow">
    <a href="#">
      <i class="fa-solid fa-arrow-up-long"></i>
    </a>
  </div>
</template>

<script>

  export default {
    name:'stickyGoTop',
  }

</script>

<style lang="scss">

  @import "@/styles/general.scss";

  .goTop{
    position: fixed;
    background-color: $cube_mountain_meadow;
    border-radius: 50%;
    font-size: 1.1rem;
    bottom: 1rem;
    right: 1rem;

    a {
      @extend .cubeWhiteColor;
      padding: 1rem 1.5rem;
      display: inline-block;
      text-shadow: 1px 1px 6px $dark_color;
    }
  }

</style>