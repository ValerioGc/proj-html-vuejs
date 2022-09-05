<template>
  <header>
  <div class="header-top">
    <!-- Logo pagina -->
    <img class="logo" src="@/assets/images/light-logo.png" alt="Logo MaxCoach">
    <!-- NavBar -->
    <nav>
      <ul>
      <!-- NavLinks -->
        <navItems v-for="(link, index) in navLinks" :key="link + index" :idx="index" :navL="navLinks" />

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
      <srcBar @usrIn="getInput(input)" />
    </nav>
  </div>


    <headerJumbo />

  </header>
</template>

<script>

  import headerJumbo from './headerJumbo.vue'
  import srcBar from './srcBar.vue'
  import navItems from './navItems.vue'

  export default {
    name:'appHeader',
    searchInput:'',
    components: {
      navItems,
      headerJumbo,
      srcBar,
    },
    props: {
      cartItems: Number,
    },
    data() {
      return {
        navLinks: [
          {
            name: 'Home',
            path: '#',
          },          {
            name: 'Pages',
            path: '#',
          },
          {
            name: 'Courses',
            path: '#',
          },
          {
            name: 'Features',
            path: '#',
          },
          {
            name: 'Blog',
            path: '#',
          },
          {
            name: 'Shop',
            path: '#',
          }
        ]
      }
    },
    methods: {
      getInput(input){
        this.searchInput = input.toLowerCase();
      }
    }
  }

</script>

<style lang="scss">

  @import "../styles/vars.scss";
  @import "../styles/general.scss";

  header {
    background-color: $cube_port_gore;

    .header-top {
      width: 70%;
      margin: auto;
      display: flex;
      justify-content: space-between;
      align-items: center;

      .logo {
        width: 15%;
      }

      nav {
        padding: 1rem 0;
        font-weight: bold;
        display: flex;
        flex-basis: 80%;
        justify-content: space-between;
        align-items: center;

        ul {
          display: flex;
          align-items: center;
          justify-content: space-between;

          .cartUser > * {
            @extend .cubeWhiteColor;

            .cartItems {
              color: $cube_port_gore;
              background-color: $cube_white;
              padding: 1px 3px;
              font-size: 0.6rem;
              border-radius: 50%;
              display: inline-block;
              position: relative;
              bottom: 12px;
              right: 5px;
            }
          }
        }
      }
    }
  }

</style>