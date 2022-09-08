<template>
  <div v-if="type === 'advisor'" class="extInfo">
    <span>{{ name }}</span>
    <span>/ {{role}}</span>
  </div>
  <div v-else class="stats">
    <span class="statsN">{{ name }}</span>
    <span class="statsT">{{ role }}</span>
  </div>
</template>

<script>

  export default {
    name:'extInfo',
    props: {
      name: String,
      role: String,
      type: String
    }
  }

</script>

<style lang="scss" scoped>

  @import "@/styles/general.scss";

  // Advisor
  .extInfo {
    @extend .t-align-c;
    display: inline-block;
    padding: 2rem 0;

    span:first-child,
    span:last-child {
      @extend .t-align-l;
      display: block!important;
    }
    span:first-child {
      @extend .uppercase;
      @extend .bold;
      padding-bottom: 0.8rem;

    }
    span:last-child {
      @extend .capitalize;
      color: $cube_dove_gray;
      font-size: 0.9rem;
    }
  }

  // Stats
  .stats {
    @extend .uppercase;
    @extend .bold;
    font-size: 1.1rem;
    padding-bottom: 2rem;

    span:first-child,
    span:last-child {
      @extend .uppercase;
      display: block!important;
    }
    span:first-child {
      color: $material_jungle_green;
      font-size: 2.5rem;
    }
  }

</style>
