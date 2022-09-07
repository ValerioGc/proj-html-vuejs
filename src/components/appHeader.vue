<template>
  <header>
    <!-- NavBar -->
    <div class="header-top responsive-container">
      <!-- Logo pagina -->
      <a class="logo"  href="#"><img src="@/assets/images/light-logo.png" alt="Logo MaxCoach" /></a>
      <nav>
        <ul>
          <!-- NavLinks -->
          <navItems :navL="navLinks" v-for="(link, index) in navLinks" :key="link + index" :idx="index"  />
          <!-- Sezione carello e login -->
          <li class="cartUser">
            <a href="#">
              <i class="fa-solid fa-cart-shopping">
                <span class="cartItems">{{ cartItems }}</span>
              </i>
            </a>
            <a href="#">
              <i class="fa-regular fa-circle-user"></i>
            </a>
          </li>
        </ul>
        <!-- Barra di ricerca -->
        <srcBar @usrIn="getInput" />
      </nav>
    </div>
    <!-- Jumbotron -->
    <headerJumbo />
  </header>
</template>

<script>

//Components
  import srcBar from './headerComponents/srcBar.vue'
  import navItems from './headerComponents/navItems.vue'
  import headerJumbo from './headerComponents/headerJumbo.vue'
// DB
  import headerData from '@/db/headerData.json';

  export default {
    name:'appHeader',
    searchInput:'',
    components: {
      navItems,
      srcBar,
      headerJumbo,
    },
    props: {
      cartItems: Number,
    },
    data() {
      return {
        navLinks: headerData.navLinks,
      }
    },
    methods: {
      getInput(input){
        this.searchInput = input.toLowerCase().trim();
      }
    }
  }

</script>

<style lang="scss">

  @import "@/styles/general.scss";

  header {
    background-color: $cube_port_gore;

    .header-top {
      @include d-flex('no', 'space-between', 'center');

      .logo {
        width: 13%;

        img {
          width: 100%;
        }
      }

      nav {
        padding: 1rem 0;
        font-weight: bold;
        @include d-flex('no', 'end', 'center');

        ul {
          @include d-flex('no', 'space-between', 'center');
          padding-right: 1rem;
          flex-basis: 85%;

          .cartUser > * {
            @extend .cubeWhiteColor;

            i:hover {
              @extend .standard-hover;
            }
            .cartItems {
              @extend .pos-relative;
              color: $cube_port_gore;
              background-color: $cube_white;
              padding: 1px 3px;
              font-size: 0.6rem;
              border-radius: 50%;
              display: inline-block;
              bottom: 12px;
              right: 5px;
            }
          }
        }
      }
    }
  }

</style>