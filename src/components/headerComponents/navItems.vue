<template>
  <li class="navL-container">
    <a :href="navL[idx].path" class="navLName">
      {{navL[idx].name}}
      <i class="fa-solid fa-angle-down"></i>
    </a>
    <ul class="dropdown">
      <li v-for="n in 3" :key="n">
        Link
      </li>
    </ul>
  </li>
</template>

<script>

  export default {
    name:'navItems',
    props: {
      navL: Array,
      idx: Number,
    }
  }

</script>

<style lang="scss" scoped>

  @import "@/styles/general.scss";

  .navL-container {

    &:hover .dropdown {
      @extend .standardTransition;
      display: block;
    }

    .navLName {
      @extend .cubeWhiteColor;
      margin-right: 1rem ;
      @extend .pos-relative;

        @media (max-width: $large) {
          font-size: 0.8rem;
          margin-right: 0.5rem ;
        }
        @media (max-width: $medium) {
          display: none;
        }

      &:hover {
        @extend .standard-hover;
      }
      &:hover .navL-container{
        transform: translateY(50px);
      }
    }
    .dropdown {
      display: none;
      position: absolute;
      background-color: $cube_silver;
      border-bottom-left-radius: 5px;
      border-bottom-right-radius: 5px;
      padding-right: 0;

      li {
        padding: 0.7rem 1.5rem;
      }
      li:not(li:last-child) {
        border-bottom: 1px solid black;
      }
    }
  }

</style>