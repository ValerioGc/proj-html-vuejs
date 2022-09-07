<template>
      <li class="card">
        <img v-if="dataSource.img !== undefined"
             :src="require('@/assets/images/'+ dataSource.img)" alt="'img card">
        <sectionTitle  :title="dataSource.title"
                        :subTitle="dataSource.text"
                        :reverse="rev"/>

        <!-- Sezione Icone -->
        <div class="icoSec-Info"
             v-if="dataSource.icons !== undefined">
          <span>
            <i class="fa-regular" :class="dataSource.icons.icoTy"></i>
            {{ dataSource.icons.icoTyText }}
          </span>
          <span class="sec-info">
            <i class="fa-regular" :class="dataSource.icons.icoTy2"></i>
            {{ dataSource.icons.icoTyText2 }}
          </span>
        </div>
      </li>
</template>

<script>

  import sectionTitle from "../common/sectionTitle.vue";

  export default {
    name: 'sectionCard',
    props: {
      dataSource: Object,
      rev: String,
    },
    components: {
      sectionTitle,
    },
  }

</script>

<style lang="scss" scoped>

  @import "@/styles/general.scss";

  .card {

    &:hover {

    }
  }


</style>