<template>
  <div class="section-container">
    <!-- Titolo Sezione -->
    <sectionTitle
        :title="dataObj.secTitle"
        :subTitle="dataObj.secSubTitle"
        :highlight="dataObj.highlight"/>
    <!-- Cards -->
    <ul class="card-container">
      <sectionCard v-for="(res, index) in dataObjDet " :key="index" :dataSource="res"/>
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
      btn: String,
      btnTy: Number,
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