<template>
      <li class="card">
        <img :src="require('@/assets/images/'+ dataSource.img)" alt="'img card">


        <!-- Sezione Icone -->
        <div class="icoSec-Info"
             v-if="dataSource.length > 0">
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

import sectionTitle from "@/components/common/sectionTitle";
export default {
  name: 'sectionCard',
  components: {
    sectionTitle
  },
  props: {
    dataSource: Object,
  }
}

</script>

<style lang="scss" scoped>

  @import "@/styles/general.scss";

  .card {

    &:hover {

    }
  }


</style>