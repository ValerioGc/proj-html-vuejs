<template>
  <div class="section-title-container">
    <p v-if="(subTitle !== undefined) && (subTitleType == undefined)" class="section-subtitle">{{ subTitle }}</p>
    <p v-if="subTitleType !== undefined" class="last-section-subtitle">
      {{ subTitle }}<span class="highlighted-sub">{{ highlight }}</span>
    </p>
    <h2 class="section-title">
      {{ title }} <span v-if="subTitleType == undefined" class="highlighted">{{ highlight }}</span> {{ title2 }}
    </h2>
  </div>
</template>

<script>

  export default {
    name:'sectionTitle',
    props: {
      title: String,
      title2: String,
      subTitle: String,
      highlight: String,
      subTitleType: String,
    }
  }

</script>

<style lang="scss">

  @import "@/styles/general.scss";

  .section-title-container {
      @extend .t-align-c;

    .highlighted {
      @extend .capitalize;
      color: $material_jungle_green;
      font-weight: lighter;
    }
    .highlighted-sub{
      @extend .capitalize;
      color: $material_jungle_green;
      font-weight: lighter;
    }

    .section-title {
        font-weight: bold;
        color: $dark_color;
        padding: 1rem 0;
        font-weight: bold;
        @extend .capitalize;
        font-size: 3rem;

    }

    .section-subtitle {
      @extend .uppercase;
      color: $material_corduray;
    }

    .last-section-subtitle {
        color: $dark_color;
        font-weight: bold;
      }
    }

  .reverse-title {
    display: flex;
    flex-direction: column-reverse;
    @extend .cubeWhiteColor;

    .section-subtitle {
      font-weight: normal;
    }
  }
</style>