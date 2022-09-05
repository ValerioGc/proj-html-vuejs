<template>
  <li>
    <a :href="linksArr[indx].url">
      {{ linksArr[indx].name }}
    </a>
  </li>
</template>

<script>

export default {
  name:'linkList',
  props: {
    linksArr: Array,
    indx: Number,
  }
}
</script>

<style lang="scss">

@import "../styles/vars.scss";
@import "../styles/general.scss";

footer {
  background-color: green;
  height: 50vh;
}
</style>