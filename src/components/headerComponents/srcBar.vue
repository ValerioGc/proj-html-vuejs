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

<style lang="scss" scoped>

  @import "@/styles/general.scss";

  .srcBar {
    @extend .pos-relative;

    #search {
      width: 100%;
      height: 3rem;
      border-radius: 5px;
      padding: 0 5px;

      @media (max-width: $large) {
        &{
          width: 80%;
        }
        @media (max-width: $medium) {
          & {
            width: 70%;
          }
          @media (max-width: $tablet) {
            & {
              display: none;
            }
          }
        }
      }
    }

    .fa-magnifying-glass {
      color: $material_jungle_green;
      position: absolute;
      top: 50%;
      right: 6%;
      transform: translateY(-50%);

      @media (max-width: $large) {
        & {
          right: 28%;
        }
        @media (max-width: $medium) {
          & {
            right: 32%;
          }
        }
      }
    }
  }

</style>