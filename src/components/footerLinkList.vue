<template>
  <ul class="">
    <li class="link-title">
      {{ title }}
    </li>
    <li class="links" v-for="(links, index) in linksArr" :key="links + index">
      <a :href="links.url">
        {{ links.name }}
      </a>
    </li>
  </ul>
</template>

<script>


  export default {
    name:'footerLinkList',
    props: {
      linksArr: Array,
      title: String,
    }
  }

</script>

<style lang="scss" scoped>


  @import "@/styles/general.scss";

  .link-title {
    font-weight: bold;
    font-size: 1.1rem;
    padding-bottom: 1rem;

    &:hover {
      text-decoration: none;
    }
  }

  .links {
    color: $median_gray_chateau;

    a {
      @extend .links;
    }
  }

</style>