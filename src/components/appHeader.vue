<template>
  <header>
    <!-- NavBar -->
    <div class="header-top responsive-container">
      <!-- Logo pagina -->
      <img class="logo" src="@/assets/images/light-logo.png" alt="Logo MaxCoach">
      <nav>
        <ul>
          <!-- NavLinks -->
          <navItems v-for="(link, index) in navLinks" :key="link + index" :idx="index"  />
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

  import srcBar from './srcBar.vue'
  import navItems from './navItems.vue'
  import headerJumbo from './headerJumbo.vue'

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
        this.searchInput = input.toLowerCase().trim();
      }
    }
  }

</script>

<style lang="scss">


  @import "../styles/general.scss";

  header {
    background-color: $cube_port_gore;

    .header-top {
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
        justify-content: space-between;
        align-items: center;

        ul {
          display: flex;
          align-items: center;
          justify-content: space-between;
          padding-right: 1rem;

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