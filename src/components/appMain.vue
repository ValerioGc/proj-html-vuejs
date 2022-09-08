<template>
  <main>
  <!-- Prima Sezione -->
    <section id="firstSec">
      <div class="section-container">
        <!-- Messaggio CEO -->
        <div class="ceo-message">
          <h3 class="txtCeo">Let passion and determinations be the guide along the way and develop at your own pace that's comfortable</h3>
          <!-- Testimonial/Stats component -->
          <extInfo :name="section1Data.name" :role="section1Data.role" :type="'advisor'" />
        </div>
        <!-- Statistiche -->
        <div class="stats-container">
          <!-- Testimonial/Stats component -->
          <extInfo v-for="(stats, index) in section1Data.statisticsMaxCoach" :key="index" :name="stats.count" :role="stats.statName"/>
        </div>
        <!-- Sezione Servizi -->
        <div class="service-section">
          <div class="container-card-services">
            <!-- Cards -->
            <ul class="card-container">
              <sectionCard v-for="(res, index) in section1Data.cards " :key="index" :rev="'reverse'" :dataSource="res"/>
            </ul>
          </div>
          <div class="container-services">
            <sectionTitle :title="section1Data.secTitle" :title2="section1Data.secTitle2" :subTitle="section1Data.secSubTitle" :highlight="section1Data.highlight"/>
            <ul>
              <li v-for="service in section1Data.servicesInsight" :key="service">
                <i class="fa-solid fa-check"></i>
                <span>{{ service }}</span>
              </li>
            </ul>
            <!-- Bottone -->
            <btnApp message="Get started for free" />
          </div>
        </div>
      </div>
    </section>

  <!-- Seconda Sezione -->
    <section id="secondSec">
      <div class="section-container">
        <!-- Titolo Sezione -->
        <sectionTitle :title="section2Data.secTitle" :subTitle="section2Data.secSubTitle" :highlight="section2Data.highlight"/>
        <!-- Cards -->
        <ul class="card-container">
          <sectionCard v-for="(res, index) in section2Data.featuredCourses " :key="index" :dataSource="res"/>
        </ul>
        <!-- Bottone -->
        <btnApp message="View all courses" :type="2" />
      </div>
    </section>

  <!-- Terza Sezione -->
    <section id="thirdSec">
      <div class="section-container">
      <!-- Titolo Sezione -->
        <sectionTitle :title="section3Data.secTitle" :title2="section3Data.secTitle2" :highlight="section3Data.highlight"/>
      <!-- Sezione Testimonials -->
        <div class="exp">
          <div class="testimonial-cont">
            <img class="testimonial-avatar" src="@/assets/images/testimonial-avata-02.jpg" alt="Img Testimonial Hollace"/>
            <img class="decoration" src="@/assets/images/maxcoach-shape-05.png" alt="svg decoration"/>
          </div>
          <div class="testimonial-text">
            <p>{{ section3Data.textSection }}</p>
          <!-- Componente Info -->
            <extInfo :name="section3Data.name" :role="section3Data.role" :type="'advisor'"/>
          </div>
        </div>
      <!-- Img Parthner -->
        <div class="parth-logo-container">
          <img v-for="(parthner, index) in section3Data.parthList" :src="require('@/assets/images/'+ parthner.logo)" :key="index + parthner" :alt="'Logo' + ' ' + parthner.name " />
        </div>
      </div>
    </section>

  <!-- Quarta Sezione -->
    <section id="fourthSec">
      <div class="section-container">
      <!-- Titolo Sezione -->
        <sectionTitle :title="section4Data.secTitle" :subTitle="section4Data.secSubTitle" :highlight="section4Data.highlight"/>
        <!-- Cards -->
        <ul class="card-container">
          <sectionCard v-for="(res, index) in section4Data.latestArticles " :key="index" :dataSource="res"/>
        </ul>
      </div>
    </section>

  <!-- Quinta Sezione -->
    <section id="fifthSec">
      <div class="section-container">
      <!-- Titolo sezione-->
        <sectionTitle :title="section5Data.secTitle" :title2="section5Data.secTitle2" :highlight="section5Data.highlight" :subTitle="section5Data.secSubTitle" />
      <!-- Cards -->
        <ul class="card-container">
          <sectionCard v-for="(res, index) in section5Data.offeredServices " :key="index" :dataSource="res" :rev="'yes'"/>
        </ul>
        <img class="fifthSec-img" src="@/assets/images/home-6-services-image.png" alt="Image fifth section" />
      </div>
    </section>

  <!-- Ultima Sezione -->
    <section id="lastSec">
      <div class="section-container">
      <!-- Titolo sezione-->
        <sectionTitle :title="section6Data.secTitle" :subTitle="section6Data.secSubTitle" :highlight="section6Data.highlight" :subTitleType="section6Data.subTitleType"/>
      <!-- Bottone -->
        <btnApp message="Get started now" :type="1" />
      </div>
    </section>
  </main>
</template>

<script>

// Components
  import extInfo from "./mainComponents/extInfo.vue";
  import sectionTitle from "./common/sectionTitle.vue";
  import sectionCard from "./mainComponents/sectionCard.vue";
  import btnApp from "./common/btnApp.vue";
// DB
  import mainData from "@/db/mainData.json"

  export default {
    name:'appMain',
    components: {
      btnApp,
      extInfo,
      sectionTitle,
      sectionCard
    },
    data() {
      return {
      // Sez 1 Data
        section1Data: mainData.section1,
      // Sez 2 Data
        section2Data: mainData.section2,
      // Sez 3 Data
        section3Data: mainData.section3,
      // Sez 4 Data
        section4Data: mainData.section4,
      // Sez 5 Data
        section5Data: mainData.section5,
      // Sez 6 Data
        section6Data: mainData.section6
      }
    }
  }

</script>

<style lang="scss">

  @import "@/styles/general.scss";

  main {
    .section-container {
      @include responsive-container(70%);
      @extend .t-align-c;
      margin: 5rem auto;
    }
    .card-container {
      @include d-flex('wrap', 'space-between', 'center')
    }
    // **** First Section ****
    #firstSec {
      background-image: url("@/assets/images/background-pattern-grid-line.png");

      // CEO Msg
      .ceo-message {
        @extend .m-auto;
        width: 65%;
        padding: 7rem 0;
        .txtCeo {
          font-size: 2rem;
          line-height: 3rem;
        }
      }
      // section stats
      .stats-container {
        @include d-flex('wrap', 'space-around', 'center');
        padding-bottom: 6rem;
      }
      // Services
      .service-section {
        @include d-flex('', 'center', 'center');

        .container-services {
          width: 40%;
          text-align: left;

          .section-title {
            font-size: 4rem;
            padding-bottom: 2rem;
          }
          .section-subtitle {
            @extend .bold;
          }

          ul li {
            @extend .capitalize;
            font-size: 1.2rem;
            padding-bottom: 1rem;

            i {
              margin-right: 1rem;
              color: $material_jungle_green;
              @extend .bold;
            }
          }

          .btn {
            margin: 1.5rem auto;
          }

        }
        .container-card-services {
          @include d-flex('wrap', 'space-between', 'center');
          height: 100%;
          width: 45%;

          .card-container {
            @include d-flex('wrap', 'space-between', 'start');
            height: 100%;
            width: 85%;

            // Cards
            & li:nth-child(2),
            & li:nth-child(4) {
              align-self: flex-end;
              margin-top: 6rem;
            }
            & li:nth-child(1),
            & li:nth-child(2) {
              display: flex;
              flex-direction: column-reverse;
            }

            .card {
              width: calc(50% - 1rem);

              border: 1px solid $dark_color;
              box-shadow: 0 0 5px -2px $dark_color;

              .rev-title-container {
                color: $dark_color;
              }
              .section-title {
                font-size: 1rem;
              }

              img {
                height: 10rem;
                width: 100%;
                object-fit: contain;
              }
            }
          }
        }
        .container-services * {
          text-align: left;
        }
      }
    }
    // **** Second Section ****
    #secondSec {
      padding: 1rem 0 0.5rem;
      @extend .sec-bg-color;

      .btn {
        margin: 5rem 0;
      }

      .card {
        @include d-flex('', 'center', 'center');
        flex-direction: row;
        padding: 1rem ;
        width: 45%;
        @media (max-width: $medium) {
          width: 100%;
          flex-wrap: wrap;
        }
        .txtCard {
          padding: 2rem ;
        }
        .section-title {
          @extend .bold;
          text-align: left;
          font-size: 1.2rem;
          padding-bottom: 1rem;
        }
        .section-subtitle {
          @extend .bold;
          text-align: left;
          font-size: 1.2rem!important;
          color: $cube_mountain_meadow;
          text-shadow: 2px 2px 2px $dark_color;
        }
        .icoSec-Info  {
          @include d-flex('wrap', 'space-between', 'center');
        }
        img {
          border-radius: 50%;
          width: 10rem;
          height: 10rem;
          object-fit: cover;
        }
        // Hover Card
        &:hover {
          border-radius: 5px;
          color: $material_jungle_green;
        }
      }
    }

    // **** Third Section ****
    #thirdSec {
      .exp {
        @include d-flex('wrap', 'space-between', 'center');
        width: 70%;
        margin: 3rem auto 5rem;
        @media (max-width: $medium) {
          justify-content: center;
        }

          .testimonial-text {
            width: 70%;
            text-align: left;
            padding: 0.2rem 0.5rem;

            p {
              font-size: 1.4rem;
            }
          }

        .testimonial-cont{
          @extend .pos-relative;
          align-self: stretch;
          padding-bottom: 1rem;

          .testimonial-avatar {
            border-radius: 50%;
            width: 10rem;
          }
          .decoration {
            position: absolute;
            transform: translate(-95%, 110%);
            z-index: -1;
            width: 6rem;
          }
      }
    }
      .parth-logo-container{
        @include d-flex('wrap', 'space-around', 'center');

        @media (max-width: $medium) {
          justify-content: center;
        }

        img {
          width: 7rem;
          object-fit: contain;
          height: 4rem;
          margin: 1rem 0;

          @media (max-width: $medium) {
            margin-right: 1rem;

          }
        }
      }
    }

    // **** Fourth Section ****
    #fourthSec {
      @extend .primary-bg-color;
      padding: 2rem 0;

      .card-container{
        @media (max-width: $medium) {
          justify-content: center;
        }

        .card {
          width: calc(30% - 1.5rem);
          padding: 1.4rem;
          @media (max-width: $medium) {
            width: 80%;
          }

          img {
            object-fit: contain;
            width: 100%;
          }

          .icoSec-Info {
            text-align: left;
            i {
              padding-right: 0.3rem;
            }
            span {
              padding-right: 1rem;
            }
          }
        }
        .section-title-container {
            text-align: left;

            .section-title {
              font-size: 1.4rem;
              padding: 1rem 0;
            }

            .section-subtitle {
              font-weight: normal;
              padding-top: 1rem;
            }
          }
        }
    }

    // **** Fifth Section ****
    #fifthSec {
      .card-container {
        @include d-flex('wrap', 'space-between', 'center');
        text-align: left;
        padding: 5rem 0;

        @media (max-width: $medium) {
          justify-content: center;
        }

        .card {
          padding: 1.8rem 1rem;
          width: 25%;
          @media (max-width: $medium) {
            width: 60%;
          }

          .section-subtitle,
          .section-title {
            color: $dark_color;
          }
          .section-title {
            font-size: 1rem;
            color: $dark_color;
          }
          .section-subtitle {
            font-size: 1rem;
            color: $cube_dove_gray;
          }
          img {
            width: 5rem;
          }
        }
      }
      .fifthSec-img {
        width: 100%;
      }
    }
  }
</style>