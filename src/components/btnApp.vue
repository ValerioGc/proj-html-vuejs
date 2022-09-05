<template>
  <a v-if="type === 2" class="btn">
    <span>{{ message }}</span>
    <i class="fa-solid fa-arrow-right-long"></i>
  </a>
  <a v-else :class="(type === 1) ? 'bt1' : 'bt2' " class="btn">{{ message }}</a>
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

<style lang="scss">

  @import "../styles/vars.scss";
  @import "../styles/general.scss";

  .btn {
    @extend .cubeWhiteColor;
    cursor: pointer;
    background-color: $material_jungle_green;
    font-weight: bold;
    padding: 15px 25px;
    border-radius: 3px;
    box-shadow: 0 0 4px -2px $dark_color;

    &:hover {
      @extend .standardTransition;
    }
  }
  // Hover Bottoni
  .bt1:hover {
      color: $material_jungle_green;
      background-color: $cube_white;
    }
  .bt2:hover {
      @extend .cubeWhiteColor;
      background-color: $material_blue_marguerite;
    }

</style>