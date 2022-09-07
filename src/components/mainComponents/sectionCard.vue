<template>
      <li class="card">
        <img :src="require('@/assets/images/'+ dataSource.img)" alt="'img card">
        <h4>{{dataSource.title}}</h4>
        <p>{{dataSource.text}}</p>
        <div class="icoSec-Info"
             v-if="dataSource.icons !== undefined">
          <span>
            <i class="fa-regular" :class="dataSource.icoTy"></i>
            {{ dataSource.icoTyText }}
          </span>
          <span class="sec-info">
            <i class="fa-regular" :class="dataSource.icoTy"></i>
            {{ dataSource.icoTyText }}
          </span>
        </div>
      </li>
</template>

<script>

export default {
  name: 'sectionCard',
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