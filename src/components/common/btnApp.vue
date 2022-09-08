<template>
  <a v-if="type === 2"  class="btn bt2">
    <span>{{ message }}</span>
    <i class="fa-solid fa-arrow-right-long"></i>
  </a>
  <a v-else class="btn bt1">{{ message }}</a>
</template>

<script>

  export default {
    name: 'btnApp',
    props: {
      message: String,
      type: Number,
    }
  }

</script>

<style lang="scss" scoped>

  @import "@/styles/general.scss";

  .btn {
    @extend .cubeWhiteColor;
    @extend .bold;
    display: inline-block;
    cursor: pointer;
    background-color: $material_jungle_green;
    padding: 1.2rem 3.5rem;
    border-radius: 6px;
    box-shadow: 0 0 4px -2px $dark_color;

    &:hover {
      @extend .standardTransition;
      border-radius: 2px;
    }

    i {
      margin-left: 4px;
    }
  }
  // Hover Buttons
  .bt1:hover {
      color: $material_jungle_green;
      background-color: $cube_white;
    }
  .bt2:hover {
      @extend .cubeWhiteColor;
      background-color: $material_blue_marguerite;
    }

</style>