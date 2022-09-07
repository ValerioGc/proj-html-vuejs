<template>
  <div class="peopleInfo">
    <span>{{ name }}</span>
    <span>/ {{role}}</span>
  </div>
</template>

<script>

export default {
  name:'nameRole',
  props: {
    name: String,
    role: String,
  }
}

</script>

<style lang="scss" scoped>

  @import "@/styles/general.scss";

  .peopleInfo {
    display: inline-block;
    padding: 2rem 0;
    text-align: center;

    span:first-child,
    span:last-child {
      display: block;
      text-align: left;
    }

    span:first-child {
      @extend .uppercase;
      padding-bottom: 0.8rem;
      font-weight: bold;
    }

    span:last-child {
      @extend .capitalize;
      color: $material_corduray;
      font-size: 0.9rem;
    }
  }

</style>