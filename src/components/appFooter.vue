<template>
  <footer>
    <div class="foot-container">
      <div class="footer-link-container">
        <!-- Link footer SX -->
        <div class="addressInfo-container">
          <!-- Address Info -->
          <ul>
            <li class="link-title">Address</li>
            <li v-for="items in companyInfo" :key="items" class="addressInfo">
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
          <footerLinkList class="info-list" :linksArr="footerLinksExplore" :title="'Explore'" />
          <!-- Info Links -->
          <footerLinkList :linksArr="footerLinksInfo" :title="'Information'" />
        </div>
      </div>
      <!-- Parte Inferiore Footer -->
      <div class="sub-footer">
        <p> &copy; {{ copyRInfo }}</p>
      </div>
    </div>
  </footer>
</template>

<script>

//Components
  import footerLinkList from "@/components/footerComponents/footerLinkList.vue";
// DB
  import footerData from '@/db/footerData.json'

  export default {
    name:'appFooter',
    components: {
      footerLinkList,
    },
    data() {
      return {
      // Company info
        companyInfo: footerData.companyInfo,
      // Social Footer
        socialLinks: footerData.socialLinks,
      // Link Footer Explore
        footerLinksExplore: footerData.footerLinksExplore,
      // Link Footer Info
        footerLinksInfo: footerData.footerLinksInfo,
      // Copyright Info
        copyRInfo: footerData.copyRInfo
      }
    }
  }

</script>

<style lang="scss">

  @import "@/styles/general.scss";

  .info-list {
    @include d-flex('wrap', 'end');
    flex-direction: column;
    height: 11rem;
    padding-right: 10rem;

      li {
        padding-right: 5rem!important;
    }
  }
  .fa-brands {
    @extend .footer-links-style;
    padding: 1rem 3rem 1rem 0;
    font-size: 2rem;

    &:hover {
      @extend .standard-hover;
    }
  }
  .list {
    @include d-flex('wrap', 'space-between');
    margin-right: 4%;
  }
  .link-title {
    color: $dark_color;
  }

  footer {
    @extend .primary-bg-color;
    margin-top: 2rem;
    box-shadow: 0 0 5px -2px $dark_color;

    .foot-container {
      @include responsive-container(70%);
      padding-top: 3rem;

      .footer-link-container{
        @include d-flex('wrap', 'space-between');

        li:not(.link-title) {
          padding: 0.6rem 0;
        }

        .addressInfo-container {
          margin-right: 2rem;
        }

        .addressInfo {
          @extend .footer-links-style;
        }

        a:hover {
          text-decoration: underline;
        }
      }
      .sub-footer {
        @extend .t-align-c;
        padding: 3rem 0;
      }
    }
  }







</style>