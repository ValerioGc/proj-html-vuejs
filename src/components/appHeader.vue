<template>
  <header>
  <div class="header-top">
    <img class="logo" src="@/assets/images/light-logo.png" alt="Logo MaxCoach">
    <nav>
      <!-- Logo pagina -->
      <!-- NavLinks -->
      <ul>
        <li v-for="(link, index) in navLinks" :key="index">
          <a href="#" class="navLName">
            {{link.name}}
            <i class="fa-solid fa-angle-down"></i>
          </a>
        </li>

        <li class="cartUser">

          <!-- <userCartLogin :cartN="cartItems" /> -->

          <!-- Sezione carello -->
          <a href="#">
            <i class="fa-solid fa-cart-shopping">
              <span class="cartItems">{{ cartItems }}</span>
            </i>
          </a>
          <!-- Login Utente -->
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

  export default {
    name:'appHeader',
    searchInput:'',
    components: {
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
        return this.searchInput;
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
      display: flex;
      justify-content: space-between;
      align-items: center;
      width: 70%;
      margin: auto;

      .logo {
        width: 15%;
      }

      nav {
        display: flex;
        padding: 1rem 0;
        align-items: center;
        justify-content: space-between;
        font-weight: bold;
        flex-basis: 80%;

        ul {
          justify-content: space-between;
          align-items: center;
          display: flex;

          .cartItems {
            @extend .cubeWhiteColor;
            background-color: $cube_white;
            border-radius: 50%;
            color: $cube_port_gore ;
            position: relative;
            bottom: 12px;
            right: 5px;
            display: inline-block;
            font-size: 0.6rem;
            padding: 1px 3px;
          }

          .navLName {
            color: $cube_white;
            padding-right: 3px ;
          }
        }
      }
    }
  }

</style>