<template>
    <ul>
      <li class="card">
        <img :src="require('@/assets/images/'+ dataSource.img)" alt="'img card">
        <h4>{{dataSource.title}}</h4>
        <p>{{dataSource.text}}</p>
      </li>
    </ul>

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