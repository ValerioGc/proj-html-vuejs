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
        <img src="../assets/images/icon-youtube-play.png" alt="logo youtube" class="youtube-logo" />
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
              require('../assets/images/home-6-hero-left-person.png'),
              require('../assets/images/home-6-hero-poster-final.jpg'),
              require('../assets/images/home-6-hero-right-person.png'),
            ]
      }
    }
  }

</script>

<style lang="scss">

  @import "../styles/vars.scss";
  @import "../styles/general.scss";

  #jumbo {
    text-align: center;
    padding: 6rem 0 0;
    position: relative;
    width: 80%;
    margin: auto;

    .jumboTitle {
      color: $cube_white;
      padding: 0 0 1rem;
      text-transform: capitalize;
    }
    p {
      @extend .cubeWhiteColor;
      padding-bottom: 3rem;
    }
    // Container Img Jumbotron
    .imgJumbo-container {
      position: relative;
      bottom: -4rem;
      display: flex;
      justify-content: center;
      flex-shrink: 0;

      .imgJumbo-01 {
        width: 20%;
        object-fit: cover;
        object-position: left;
      }

      .imgJumbo-02 {
        border: 1rem solid $cube_white;
        border-radius: 30px;
        width: 60%;
        margin: 0 0 2rem;
      }

      .imgJumbo-03 {
        width: 20%;
        padding-right: 5rem;
        height: 8rem;
        object-fit: cover;
        object-position: top;
        align-self: flex-end;
      }

      .youtube-logo{
        position: absolute;
        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%);
      }
    }
  }

</style>