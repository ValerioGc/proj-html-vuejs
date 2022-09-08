<template>
  <div class="section-container">
    <!-- Titolo Sezione -->
    <sectionTitle
        :title="dataObj.secTitle"
        :title2="dataObj.secTitle2"
        :subTitle="dataObj.secSubTitle"
        :highlight="dataObj.highlight" />
    <!-- Cards -->
    <ul v-if="cards !== undefined" class="card-container">
      <sectionCard v-for="(res, index) in dataObjDet " :key="index"
                   :dataSource="res"
                   :rev="revs" />
    </ul>
    <!-- Bottone -->
    <btnApp v-if="btn !== undefined" message="View all courses" :type="btnTy" />
  </div>
</template>

<script>

  import sectionTitle from "@/components/common/sectionTitle.vue";
  import sectionCard from "@/components/mainComponents/sectionCard.vue";
  import btnApp from "@/components/common/btnApp.vue";

  export default {
    name:'mainSection',
    props: {
      dataObj: Object,
      dataObjDet: Array,
      cards: String,
      btn: String,
      btnTy: Number,
      revs: String,
    },
    components: {
      btnApp,
      sectionTitle,
      sectionCard
    }
  }

</script>

<style lang="scss">

  @import "@/styles/general.scss";

  .section-container {
    @include responsive-container(70%);
    @extend .t-align-c;
    margin: 5rem auto;

    .card-container {
      @include d-flex('wrap', 'space-between', 'center')
    }
  }

</style>