<template>
  <footer>
    <div class="foot-container responsive-container">
      <div class="footer-link-container">
        <!-- Link footer SX -->
        <div class="addressInfo-container">
          <!-- Address Info -->
          <ul>
            <li class="link-title">Address</li>
            <li v-for="items in companyInfo" :key="items">
              {{items}}
            </li>
            <li>
              <a v-for="(link, index) in socialLinks" :href="link.url" :key="index">
                <i :class="link.icon" class="fa-brands"></i>
              </a>
            </li>
          </ul>
        </div>
        <!-- Link footer DX -->
        <div class="list">
          <!-- Explore Links -->
          <linkList class="info-list" :linksArr="footerLinksExplore" :title="'Explore'" />
          <!-- Info Links -->
          <linkList :linksArr="footerLinksInfo" :title="'Information'" />
        </div>
      </div>
      <!-- Parte Inferiore Footer -->
      <div class="sub-footer">
        <p>&copy;2020 Maxcoach. All Rights Reserved</p>
      </div>
    </div>
  </footer>
</template>

<script>

  import linkList from "@/components/linkList.vue";

  import footerData from '@/db/footerData.json'

  export default {
    name:'appFooter',
    components: {
      linkList,
    },
    data() {
      return {
        // Company info
        companyInfo: footerData.companyInfo,
        /* companyInfo: {
    geo:'382 NE 191st ST # 873394 Miami, FL 33179-3899',
    phone:'+1(305)547- 9909 (9am-5pm EST, Monday - Friday)',
    email:'support@maxcoach.com'
  }, */
        // Social Footer
        socialLinks: footerData.socialLinks,
        /* socialLinks: [
  {
    icon:'fa-square-facebook',
    url:'https://facebook.com',
  },
  {
    icon:'fa-twitter',
    url:'https://twitter.com',
  },         {
    icon:'fa-instagram',
    url:'https://instagram.com',
  },
  {
    icon:'fa-linkedin',
    url:'https://linkedin.com',
  }
],*/
        // Link Footer Explore
        footerLinksExplore: footerData.footerLinksExplore,
        /* footerLinksExplore: [
  {
    name:'Start Here',
    url:'#',
  },
  {
    name:'Blog',
    url:'#',
  },         {
    name:'About us',
    url:'#',
  },
  {
    name:'Success story',
    url:'#',
  },
  {
    name:'Courses',
    url:'#',
  },
  {
    name:'Contact us',
    url:'#',
  }
],*/
        // Link Footer Info
        footerLinksInfo: footerData.footerLinksInfo,
        /* footerLinksInfo: [
  {
    name:'Membership',
    url:'#',
  },
  {
    name:'Purchase guide',
    url:'#',
  },         {
    name:'Privacy policy',
    url:'#',
  },
  {
    name:'Team of services',
    url:'#',
  }
],*/
      }
    }
  }
</script>

<style lang="scss">

  @import "../styles/general.scss";


  .info-list {
    padding-right: 10rem;
    display: flex;
    flex-direction: column;
    justify-content: flex-end;
    height: 9rem;
    flex-wrap: wrap;

      li {
        padding-right: 5rem!important;
    }
  }
  .list {
    display: flex;
    justify-content: space-between;
  }
  .link-title {
    color: $dark_color;
  }

  footer {
    background-color: green;

    .foot-container {
      padding-top: 3rem;

      .footer-link-container{
        display: flex;
        justify-content: space-between;

        li {
          padding: 5px 0;
        }

        .addressInfo-container {

        }

        .addressInfo {

        }
        a:hover {
          text-decoration: underline;
        }
      }
      .sub-footer {
        text-align: center;
        padding: 3rem 0;


      }
    }
  }







</style>