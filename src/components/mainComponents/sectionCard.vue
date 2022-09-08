<template>
      <li class="card">
        <img v-if="dataSource.img !== undefined" :src="require('@/assets/images/'+ dataSource.img)" alt="'img card">
        <div class="txtCard">
          <sectionTitle  :title="dataSource.title"
                         :subTitle="dataSource.text"
                         :reverse="rev"/>
          <!-- Sezione Icone -->
          <div class="icoSec-Info"  v-if="dataSource.icons !== undefined">
            <span>
              <i class="fa-regular" :class="dataSource.icons.icoTy"></i>
              {{ dataSource.icons.icoTyText }}
            </span>
              <span class="sec-info">
              <i class="fa-regular" :class="dataSource.icons.icoTy2"></i>
              {{ dataSource.icons.icoTyText2 }}
            </span>
          </div>
        </div>
      </li>
</template>

<script>

  import sectionTitle from "@/components/common/sectionTitle.vue";

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
    cursor: pointer;

    &:hover {
      @extend .standardTransition;
      background-color: $cube_white;
      box-shadow: 0 0 5px -2px $dark_color;
    }
  }

</style>