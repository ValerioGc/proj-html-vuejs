<template>
  <div id="jumbo" class="responsive-container ">
    <div>
      <h1 class="jumboTitle capitalize">learn at your own pace!</h1>
      <p>Get teamed up with people of the same will.</p>
      <!-- Bottone -->
      <btnApp :message="'Get started for free'" :type="1"/>
    </div>
    <div class="imgJumbo-container">
        <img v-for="(img, index) in jumboImg" :src="jumboImg[index]" :class="'imgJumbo-0' +  (index + 1)" :key="img" :alt="'jumbotron image' + ' ' + index" />
        <img src="@/assets/images/icon-youtube-play.png" alt="logo youtube" class="yt  center-absolute" />
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

<style lang="scss" >

  @import "@/styles/general.scss";

  #jumbo {
    @extend .cubeWhiteColor;
    position: relative;
    width: 80%;
    margin: auto;
    padding: 6rem 0 0;
    text-align: center;

    .jumboTitle {
      padding: 0 0 1rem;
    }

    p {
      padding-bottom: 3rem;
    }
    // Container Img Jumbotron
    .imgJumbo-container {
      position: relative;
      top: 5rem;
      display: flex;
      justify-content: center;
      margin-top: 1rem;

      .imgJumbo-01 {
        width: 25%;
        object-fit: cover;
        object-position: left;
        height: 30rem;
      }

      .imgJumbo-02 {
        width: 50%;
        margin-bottom: 2.5rem;
        border: 1rem solid #ffffff;
        border-radius: 30px;
        box-shadow: 0 0 5px -1px $dark_color;
      }

      .imgJumbo-03 {
        width: 25%;
        height: 9rem;
        padding-right: 9.5rem;
        align-self: flex-end;
        object-fit: cover;
        object-position: top;
      }

      .yt {
        cursor: pointer;

        &:hover {
          filter: brightness(80%);
        }
      }
    }
  }

</style>