<template>
  <footer>
   <div class="footer-link-container">
     <div>
       <!-- Address Info -->
       <ul>
         <li>Address</li>
         <li v-for="items in addressInfo" :key="items">{{ items }}</li>
         <li>
           <a href="#">
             <i class="fa-brands fa-square-facebook"></i>
           </a>
           <a href="#">
             <i class="fa-brands fa-twitter"></i>
           </a>
           <a href="#">
             <i class="fa-brands fa-instagram"></i>
           </a>
           <a href="#">
             <i class="fa-brands fa-linkedin"></i>
           </a>
         </li>
       </ul>
     </div>
     <div>
      <!-- Explore Links -->
       <ul>
         <li>Explore</li>
         <linkList v-for="(links, index) in footerLinksExplore" :key="links + index" :indx="index" :linksArr="footerLinksExplore"/>
       </ul>
       <!-- Info Links -->
       <ul>
         <li>Information</li>
         <linkList v-for="(links, index) in footerLinksInfo" :key="links + index" :linksArr="footerLinksInfo" :indx="index"  />
       </ul>
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
        addressInfo:
          {
            geo:'382 NE 191st ST # 873394 Miami, FL 33179-3899',
            phone:'+1(305)547- 9909 (9am-5pm EST, Monday - Friday)',
            email:'support@maxcoach.com'
          },
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
    height: 50vh;
  }
</style>