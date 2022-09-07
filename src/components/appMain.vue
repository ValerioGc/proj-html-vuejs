<template>
  <main>
    <!-- Prima Sezione -->
    <section id="firstSec">
      <div class="section-container">
        <div class="ceo-message">
          <h3 class="txtCeo">Let passion and determinations be the guide along the way and develop at your own pace that's comfortable</h3>
          <!-- Testimonial component -->
          <nameRole :name="section3Data.name" :role="section1Data.role"/>
        </div>
        <!-- Statistiche -->
        <div class="stats-container">
          <div v-for="(stat, index) in section1Data.statisticsMaxCoach" :key="index" class="stats">
            <p class="uppercase statsN">{{ stat.count }}</p>
            <p class="uppercase">{{stat.statName}}</p>
          </div>
        </div>
        <!-- Sezione Servizi -->
        <div class="service-section">
          <div class="container-card-services">

          </div>
          <div class="container-services">
            <sectionTitle :title="section1Data.secTitle"
                          :title2="section1Data.secTitle2"
                          :subTitle="section1Data.secSubTitle"
                          :highlight="section1Data.highlight"/>
            <ul>
              <li v-for="service in section1Data.servicesInsight" :key="service">
                <i class="fa-solid fa-check"></i>
                <span>{{ service }}</span>
              </li>
            </ul>
            <btnApp message="Get started for free" />
          </div>
        </div>
      </div>
    </section>



    <!-- Seconda Sezione -->
    <section id="secondSec">
      <div class="section-container">
        <!-- Titolo Sezione -->

        <sectionTitle :title="section2Data.secTitle"
                      :subTitle="section2Data.secSubTitle"
                      :highlight="section2Data.highlight"/>


        <!-- Cards -->
        <ul class="card-container">
          <sectionCard v-for="(res, index) in section2Data.featuredCourses "
                       :key="index"
                       :dataSource="res"/>
        </ul>
        <!-- Bottone -->
        <btnApp message="View all courses" :type="2" />

      </div>
    </section>

    <!-- Terza Sezione -->
    <section id="thirdSec">
      <div class="section-container">
        <!-- Titolo Sezione -->
        <sectionTitle :title="section3Data.secTitle"
                      :title2="section3Data.secTitle2"
                      :highlight="section3Data.highlight"/>

        <!-- Sezione Testimonials -->
        <div class="exp">
          <img src="@/assets/images/testimonial-avata-02.jpg" alt="Img Testimonial Hollace">
          <div>
            <p>{{ section3Data.textSection }}</p>
            <nameRole :name="section3Data.name" :role="section3Data.role"/>
          </div>
        </div>
        <div>
          <img v-for="(parthner, index) in section3Data.parthList"
               :src="require('@/assets/images/'+ parthner.logo)"
               :key="index + parthner" :alt="'Logo' + ' ' + parthner.name " />
        </div>
      </div>
    </section>


    <!-- Quarta Sezione -->
    <section id="fourthSec">
      <div class="section-container">
      <!-- Titolo Sezione -->
        <sectionTitle :title="section4Data.secTitle"
                      :subTitle="section4Data.secSubTitle"
                      :highlight="section4Data.highlight"/>
        <!-- Cards -->
        <ul class="card-container">
          <sectionCard v-for="(res, index) in section4Data.latestArticles "
                       :key="index"
                       :dataSource="res"/>
        </ul>
      </div>
    </section>

  <!-- Quinta Sezione -->
    <section id="fifthSec">
      <div class="section-container responsive-container">
      <!-- Titolo sezione-->
        <sectionTitle :title="section5Data.secTitle"
                      :title2="section5Data.secTitle2"
                      :highlight="section5Data.highlight"
                      :subTitle="section5Data.secSubTitle" />
      <!-- Cards -->
        <ul class="card-container">
          <sectionCard v-for="(res, index) in section5Data.offeredServices "
                       :key="index"
                       :dataSource="res"
                       :rev="'yes'"/>
        </ul>
        <img style="width: 100%" src="@/assets/images/home-6-services-image.png" alt="Image section" />
      </div>
    </section>

  <!-- Ultima Sezione -->
    <section id="lastSec">
      <div class="section-container">
        <!-- Titolo sezione-->
        <sectionTitle :title="section6Data.secTitle"
                      :subTitle="section6Data.secSubTitle"
                      :highlight="section6Data.highlight"
                      :subTitleType="section6Data.subTitleType"/>
        <!-- Bottone -->
        <btnApp message="Get started now" :type="1" />
      </div>
    </section>

  </main>
</template>

<script>

// Components
  import nameRole from "./mainComponents/nameRole.vue"
  import sectionTitle from "./common/sectionTitle.vue"
  import sectionCard from "./mainComponents/sectionCard.vue"
  import btnApp from "./common/btnApp.vue";
// DB
  import mainData from "@/db/mainData.json"

  export default {
    name:'appMain',
    components: {
      btnApp,
      nameRole,
      sectionTitle,
      sectionCard
    },
    data() {
      return {
        // Sez 1 Data
        section1Data: mainData.section1,

        // Sez 2 Data

        section2Data: mainData.section2,
        featuredCourses: mainData.section2.featuredCourses,


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

.exp {
  @include d-flex('wrap', 'space-between', 'center');
width: 70%;
  @extend .m-auto;
}
  .service-section {
    @include d-flex('wrap', 'space-between', 'center');
  }
// **** First Section ****
  .ceo-message{
    @extend .m-auto;
    width: 55%;
    padding: 6rem 0;

    .txtCeo {
      font-size: 2rem;
      line-height: 3rem;
    }
  }

  #fifthSec ul li {
    text-align: left;
    list-style: none;
    display: inline-block;
    width: 15%;
    padding: 6rem 2rem 8rem 0;
  }
  .section-container {
    @include responsive-container(70%);
    @extend .t-align-c;
    padding: 5rem 0;
  }

  main {


      #firstSec {
        background-image: url("@/assets/images/background-pattern-grid-line.png");
      }
      #secondSec {
          @extend .sec-bg-color;
        }
      #fourthSec {
        @extend .primary-bg-color;
      }
      // Sezione statistiche
      .stats-container {
        padding-bottom: 6rem;

        .statsN {
          color: $material_jungle_green;
          font-size: 2.5rem;
        }
        .stats {
          @extend .uppercase;
          display: inline-block;
          padding: 1rem 2rem;
          font-weight: bold;
          font-size: 1.1rem;
        }
      }
  }

</style>