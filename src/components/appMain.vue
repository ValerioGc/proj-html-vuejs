<template>
  <main>
    <i class="fa-solid fa-check"></i>


    <i class="fa-regular fa-file-lines"></i>
    <i class="fa-regular fa-user"></i>




    <i class="fa-regular fa-calendar"></i>
    <i class="fa-solid fa-eye"></i>
  </main>
</template>

<script>

  export default {
    name:'appMain',
  }

</script>

<style lang="scss">

  @import "../styles/vars.scss";
  @import "../styles/general.scss";

  main {
    background-color: $median_hint_of_red;
    height: 100vh;
    background-image: url("../assets/images/background-pattern-grid-line.png");

  }

</style>