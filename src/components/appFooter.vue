<template>
  <footer>
    <div class="footer-link-container">
      <!-- Link footer SX -->
      <div>
        <!-- Address Info -->
        <ul>
          <li class="link-title">Address</li>
          <li v-for="items in addressInfo" :key="items">
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
      <div>
        <!-- Explore Links -->
        <linkList :linksArr="footerLinksExplore" :title="'Explore'" />
        <!-- Info Links -->
        <linkList :linksArr="footerLinksInfo" :title="'Information'" />
      </div>
    </div>
    <!-- Parte Inferiore Footer -->
    <div class="sub-footer">
      <p>&copy;2020 Maxcoach. All Rights Reserved</p>
    </div>
  </footer>
</template>

<script>

  import linkList from "@/components/linkList.vue";

  export default {
    name:'appFooter',
    components: {
      linkList,
    },
    data() {
      return {
        addressInfo: {
            geo:'382 NE 191st ST # 873394 Miami, FL 33179-3899',
            phone:'+1(305)547- 9909 (9am-5pm EST, Monday - Friday)',
            email:'support@maxcoach.com'
          },
        socialLinks: [
          {
            icon:'fa-square-facebook',
            url:'#',
          },
          {
            icon:'fa-twitter',
            url:'#',
          },         {
            icon:'fa-instagram',
            url:'#',
          },
          {
            icon:'fa-linkedin',
            url:'#',
          }
        ],
        footerLinksExplore: [
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
        ],
        footerLinksInfo: [
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
        ],
      }
    }
  }
</script>

<style lang="scss">

  @import "../styles/vars.scss";
  @import "../styles/general.scss";

  .footer-link-container{
    display: flex;
  }
.sub-footer {
  text-align: center;
  padding: 5rem 0;
}
  footer {
    background-color: green;

    a:hover {
      text-decoration: underline;
    }
  }


</style>