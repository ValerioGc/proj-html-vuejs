<template>
  <div class="srcBar">
    <input v-model="userInput" @change="$emit('usrIn', userInput)" type="text" id="search" placeholder="Search..." />
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

  @import "../styles/general.scss";

  .srcBar {
    position: relative;

    #search {
      width: 100%;
      height: 3rem;
      border-radius: 5px;
      padding: 0 5px;
    }

    .fa-magnifying-glass {
      color: $material_jungle_green;
      position: absolute;
      top: 50%;
      right: 6%;
      transform: translateY(-50%);
    }
  }

</style>