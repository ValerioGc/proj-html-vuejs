<template>
  <div id="jumbo" class="responsive-container ">
    <div>
      <!-- Titolo -->
      <sectionTitle :reverse="'reverse'" :title="'Learn at your Own Pace!'" :subTitle="'get teamed up with people of the same will.'"/>
      <!-- Bottone -->
      <btnApp :message="'Get started for free'" :type="1"/>
    </div>
    <!-- Container img -->
    <div class="imgJumbo-container">
        <img v-for="(img, index) in jumboImg" :src="jumboImg[index]" :class="'imgJumbo-0' +  (index + 1)" :key="img" :alt="'jumbotron image' + ' ' + index" />
        <img src="@/assets/images/icon-youtube-play.png" alt="logo youtube" class="yt  center-absolute" />
    </div>
  </div>
</template>

<script>

  import btnApp from '../common/btnApp.vue'
  import sectionTitle from '../common/sectionTitle.vue'

  export default {
    name: 'headerJumbo',
    components: {
      btnApp,
      sectionTitle,
    },
    data() {
      return {
      // Img jumbo
        jumboImg:
            [
              require('@/assets/images/home-6-hero-left-person.png'),
              require('@/assets/images/home-6-hero-poster-final.jpg'),
              require('@/assets/images/home-6-hero-right-person.png')
            ],
      }
    }
  }

</script>

<style lang="scss" scoped>

  @import "@/styles/general.scss";

  #jumbo {
    @extend .pos-relative;
    @extend .m-auto;
    @extend .t-align-c;
    @extend .cubeWhiteColor;
    @include responsive-container(80%);
    padding-top: 6rem ;

    .jumboTitle {
      padding-bottom: 1rem;
    }

    p {
      padding-bottom: 3rem;
    }

    // Container Img Jumbotron
    .imgJumbo-container {
      @include d-flex('no', 'center');
      @extend .pos-relative;
      top: 5rem;
      margin-top: 1rem;

      .imgJumbo-01,
      .imgJumbo-03 {
        width: 24%;
        object-fit: cover;
      }

      .imgJumbo-01 {
        object-position: left;
      }

      .imgJumbo-02 {
        width: 52%;
        margin-bottom: 2.5rem;
        border: 1rem solid $cube_white;
        border-radius: 30px;
        box-shadow: 2px 5px 9px -3px $dark_color;
      }

      .imgJumbo-03 {
        height: 10rem;
        padding-right: 13%;
        align-self: flex-end;
        object-position: top;

        @media (max-width: $tablet) {
          height: unset;
          padding-right: 4%;
        }
      }

      .yt {
        cursor: pointer;
        width: 8%;

        &:hover {
          filter: brightness(80%);
        }
      }
    }
  }

</style>