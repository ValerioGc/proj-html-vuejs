<template>
  <div id="jumbo">
    <div>
      <h1 class="jumboTitle">learn at your own pace!</h1>
      <p>Get teamed up with people of the same will.</p>
      <!-- Bottone -->
      <btnApp :message="'Get started for free'" :type="1"/>
    </div>
    <div class="imgJumbo-container">
        <img v-for="(img, index) in jumboImg" :src="jumboImg[index]" :class="'imgJumbo-0' +  (index + 1)" :key="img" :alt="'jumbotron image' + ' ' + index" />
        <img src="@/assets/images/icon-youtube-play.png" alt="logo youtube" class="center-absolute" />
    </div>


  </div>
</template>

<script>

  import btnApp from './btnApp.vue'

  export default {
    name: 'headerJumbo',
    components: {
      btnApp,
    },
    data() {
      return {
        jumboImg:
            [
              require('@/assets/images/home-6-hero-left-person.png'),
              require('@/assets/images/home-6-hero-poster-final.jpg'),
              require('@/assets/images/home-6-hero-right-person.png'),
            ],
      }
    }
  }

</script>

<style lang="scss">

  @import "../styles/vars.scss";
  @import "../styles/general.scss";

  #jumbo {
    @extend .cubeWhiteColor;
    position: relative;
    width: 80%;
    margin: auto;
    padding: 6rem 0 0;
    text-align: center;

    .jumboTitle {
      padding: 0 0 1rem;
      text-transform: capitalize;
    }

    p {
      padding-bottom: 3rem;
    }
    // Container Img Jumbotron
    .imgJumbo-container {
      position: relative;
      top: 4rem;
      display: flex;
      justify-content: center;

      .imgJumbo-01 {
        width: 20%;
        object-fit: cover;
        object-position: left;
      }

      .imgJumbo-02 {
        width: 60%;
        margin-bottom:2rem;
        border: 1rem solid $cube_white;
        border-radius: 30px;
      }

      .imgJumbo-03 {
        width: 20%;
        height: 8rem;
        padding-right: 5rem;
        align-self: flex-end;
        object-fit: cover;
        object-position: top;
      }
    }
  }

</style>