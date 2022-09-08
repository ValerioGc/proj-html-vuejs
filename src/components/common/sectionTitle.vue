<template>
  <div :class="(reverse === undefined ) ? 'section-title-container':'rev-title-container'">
    <p v-if="(subTitle !== undefined) && (subTitleType === undefined)" class="section-subtitle">{{ subTitle }}</p>
    <p v-if="subTitleType !== undefined" class="last-section-subtitle">
      {{ subTitle }}<span class="highlighted">{{ highlight }}</span>
    </p>
    <h2 class="section-title">
      {{ title }} <span v-if="subTitleType === undefined" class="highlighted">{{ highlight }}</span> {{ title2 }}
    </h2>
  </div>
</template>

<script>

  export default {
    name:'sectionTitle',
    props: {
      reverse: String,
      title: String,
      title2: String,
      subTitle: String,
      highlight: String,
      subTitleType: String,
    }
  }

</script>

<style lang="scss" scoped>

  @import "@/styles/general.scss";

  .highlighted {
    @extend .capitalize;
    color: $material_jungle_green;
    font-weight: lighter;
  }
  .standard-title {
    @extend .capitalize;
    @extend .bold;
    padding: 0.7rem 0 ;
    font-size: 2rem;
  }

  .rev-title-container {
    @extend .cubeWhiteColor;
    display: flex;
    flex-direction: column-reverse;
    padding-bottom: 2.5rem;

    .section-title {
      @extend .standard-title;
    }

    .section-subtitle {
      text-transform: initial;
      font-size: 1.2rem;

      &:first-letter {
        text-transform: uppercase!important;
      }
    }
  }

  .section-title-container {
      @extend .t-align-c;

      .section-title {
        @extend .standard-title;
          color: $dark_color;
          padding-bottom: 3.5rem;
      }

      .section-subtitle {
        @extend .uppercase;
        color: $cube_dove_gray;
        font-weight: normal;
      }

      .last-section-subtitle {
          @extend .bold;
          color: $dark_color;
        }
      }

</style>