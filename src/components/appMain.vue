<template>
  <main>
    <!-- Prima Sezione -->
    <section>
      <div class="section-container responsive-container">
        <div>
          <h3>Let passion and determinations be the guide along the way and develop at your own pace that's comfortable</h3>
          <p>Fannie Moreno</p>
          <span>/Founder & CEO</span>
        </div>
        <!-- Statistiche -->
        <div v-for="(stat, index) in statisticsMaxCoach" :key="index" class="stats">
          <p class="uppercase statsN">{{ stat.count }}</p>
          <p class="uppercase stats">{{stat.statName}}</p>
        </div>
        <!-- Sezione Servizi -->
        <div>
          <sectionTitle :title="'Services we'"
                        :title2="'for my clients.'"
                        :subTitle="'together we can create'"
                        :highlight="'can provide'"
                        />
          <ul>
            <li v-for="index in servicesInsight" :key="index">
              <i class="fa-solid fa-check"></i>
              <span>{{ servicesInsight[index] }}</span>
            </li>
          </ul>
          <btnApp message="Get started for free" />
        </div>
      </div>
    </section>



    <!-- Seconda Sezione -->
    <section>
      <div class="section-container responsive-container">
        <sectionTitle :title="'Latest featured'"
                      :subTitle="'chose a course to get started'"
                      :highlight="'courses'"/>
        <!-- <p>Choose a course to get started</p>
        <h2 class="capitalize">Latest featured <span>courses</span></h2> -->
        <btnApp message="View all courses" :type="2" />

        <i class="fa-regular fa-file-lines"></i>
        <i class="fa-regular fa-user"></i>
      </div>
    </section>

    <!-- Terza Sezione -->
    <section>
      <div class="section-container responsive-container">
        <sectionTitle :title="'why people talk about'"
                      :title2="'?'"
                      :highlight="'maxCoach'"/>
        <!-- <p>Choose a course to get started</p>
        <h2 class="capitalize">Latest featured <span>courses</span></h2> -->
        <btnApp message="View all courses" :type="2" />
        <div>
          <img src="" alt="">
          <div></div>
        </div>
        <div>
          <img v-for="(name, index) in parthList"  :src="parthList.logo" :key="index + name" :alt="'Logo' + ' ' + parthList.name " />
        </div>
      </div>
    </section>


    <!-- Quarta Sezione -->
    <section>
      <div class="section-container responsive-container">
        <sectionTitle :title="'Latest on'"
                      :subTitle="'enjoy reading on maxcoach'"
                      :highlight="'Our Blogs'"/>

        <i class="fa-regular fa-calendar"></i>
        <i class="fa-solid fa-eye"></i>
        <ul>
          <li>

          </li>
          <li>

          </li>
          <li>
          </li>
        </ul>
      </div>
    </section>

    <!-- Quinta Sezione -->
    <section>
      <div class="section-container responsive-container">
        <sectionTitle :title="'Glad to'"
                      :title2="'Learn'"
                      :subTitle="'wanna transform Your Life?'"
                      :highlight="'Help You'"/>
        <ul>
          <li v-for="(res, index) in offeredServices " :key="index">
            <h4>
              {{res.title}}</h4>
            <p>{{res.text}}</p>
          </li>
        </ul>
        <img src="@/assets/images/home-6-services-image.png" alt="Image section" />
      </div>
    </section>

    <!-- Sesta Sezione -->
    <section style="text-align: center">
      <div class="section-container responsive-container">
        <sectionTitle :title="'Start today for getting'"
                      :title2="'Learn'"
                      :subTitle="'You can be your own guiding star with our help!'"
                      :subTitleType="'highlight'"
                      :highlight="'Online Certification'"/>
        <btnApp message="Get started now" :type="1" />
      </div>
    </section>
    

  </main>
</template>

<script>

// Components
  import sectionTitle from "./sectionTitle.vue"
  import btnApp from "./btnApp.vue";
// DB
  import mainData from "@/db/mainData.json"

  export default {
    name:'appMain',
    components: {
      btnApp,
      sectionTitle,
    },
    data() {
      return {
        // Sez 1 Data
        statisticsMaxCoach: mainData.statisticsMaxCoach,
        // statisticsMaxCoach: mainData.section1.statisticsMaxCoach,
        servicesInsight: [
            'Select & customize to your preferences',
            'change the tutor and make arrangements',
            'partecipate in events to join others',
            'Get the desired certificate delivered at house'
        ],
        /* servicesInsight: mainData.section1.servicesInsight*/


        // Sez 2 Data
        featuredCourses: mainData.featuredCourses,
        // featuredCourses: mainData.section2.featuredCourses,

        // Sez 3 Data
        parthList: mainData.parthList,
        // parthList: mainData.section3.parthList,

        // Sez 4 Data
        latestArticles: mainData.latestArticles,
        // latestArticles: mainData.section4.latestArticles,

        // Sez 5 Data
        offeredServices: mainData.offeredServices,
        // offeredServices: mainData.section5.offeredServices,

        // Sez 6 Data

      }
    }
  }

</script>

<style lang="scss">

  @import "@/styles/general.scss";

  section {
    margin: 10rem 0;
  }
  main {
    background-color: $median_hint_of_red;
    background-image: url("@/assets/images/background-pattern-grid-line.png");


    .statsN {
      color: $material_jungle_green;
      font-weight: bold;
      font-size: 1.5rem;
    }
    .stats {
      display: inline-block;
    }
  }

</style>