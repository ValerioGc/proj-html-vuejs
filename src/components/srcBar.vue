<template>
  <div class="srcBar">
    <input v-bind="userInput" @change="$emit('usrIn', userInput)" type="text" id="search" placeholder="Search..." />
    <i class="fa-solid fa-magnifying-glass"></i>
  </div>
</template>

<script>

  export default {
    name:'srcBar',
    data(){
      return {
        userInput: '',
      }
    }
  }

</script>

<style lang="scss">

  @import "../styles/vars.scss";
  @import "../styles/general.scss";

  .srcBar {
    position: relative;
    flex-basis: 20%;

    #search {
      border-radius: 5px;
      padding: 10px 8px;
    }

    .fa-magnifying-glass {
      position: absolute;
      font-weight: bold;
      color: $material_jungle_green;
      top: 50%;
      transform: translateY(-50%);
      right: 6%;
    }
  }

</style>