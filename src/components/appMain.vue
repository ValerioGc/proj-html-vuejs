<template>
  <main>
    <!-- Prima Sezione -->
    <section style="text-align: center; padding: 5rem 0;">
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

      <btnApp message="Get started for free" />
      <i class="fa-solid fa-check"></i>
    </section>



    <!-- Seconda Sezione -->
    <section>

      <p>Choose a course to get started</p>
      <h2 class="capitalize">Latest featured <span>courses</span></h2>

      <btnApp message="View all courses" :type="2" />

      <i class="fa-regular fa-file-lines"></i>
      <i class="fa-regular fa-user"></i>
    </section>

    <!-- Terza Sezione -->
    <section>

      <h2 class="capitalize">why people talk about <span>maxCoach</span>?</h2>
      <div>
        <img src="" alt="">
        <div></div>
      </div>
      <div>
        <img v-for="(name, index) in parthList"  :src="parthList.logo" :key="index + name" :alt="'Logo' + ' ' + parthList.name " />
      </div>

      <i class="fa-regular fa-file-lines"></i>
      <i class="fa-regular fa-user"></i>
    </section>


    <!-- Quarta Sezione -->
    <section>
      <p></p>
      <h2>Latest on <span>Our Blogs</span></h2>

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
    </section>

    <!-- Quinta Sezione -->
    <section>

      <p>wanna transform Your Life</p>
      <h2>Glad to <span>Help You</span> Learn</h2>

      <ul>
        <li v-for="(res, index) in offeredServices " :key="index">
          <h4>
            {{res.title}}</h4>
          <p>{{res.text}}</p>
        </li>
      </ul>
      <img src="@/assets/images/home-6-services-image.png" alt="Image section" />

    </section>

    <!-- Sesta Sezione -->
    <section style="text-align: center">
      <p>
        Start today for getting Online Certification<span>Our Blogs</span>
      </p>
      <h2>You can be your own guiding star with our help!</h2>
      <btnApp message="Get started now" :type="1" />

    </section>
    

  </main>
</template>

<script>

  import btnApp from "./btnApp.vue";

  export default {
    name:'appMain',
    components: {
      btnApp,
    },
    data() {
      return {
        // Sez 1 Data
        statisticsMaxCoach: [
          {
            count:'1.926',
            statName:'finished sessions',
          },
          {
            count:'3.092+',
            statName:'enrolled learners',

          },
          {
            count:'200',
            statName:'online instructors',

          },
          {
            count:'100%',
            statName:'statisfaction rate',
          }
        ],
        // Sez 3 Data
        parthList: [
          {
            logo: require('@/assets/images/client-logo-colored-01.png'),
            name: 'Aqua',
          },
          {
            logo: require('@/assets/images/client-logo-colored-02.png'),
            name: 'AdRoll',
          },
          {
            logo: require('@/assets/images/client-logo-colored-03.png'),
            name: 'Firefox',
          },
          {
            logo: require('@/assets/images/client-logo-colored-04.png'),
            name: 'Woodland',
          },
          {
            logo: require('@/assets/images/client-logo-colored-05.png'),
            name: 'BullFit',
          },
          {
            logo: require('@/assets/images/client-logo-colored-06.png'),
            name: 'Sixbase',
          }
        ],
        // Sez 4 Data
        offeredServices: [
          {
            title:'Idea Discussion',
            text:'Get teamed up with the specialists who work and teach coding for years at famous universities.',
          },
          {
            title:'Web Developement',
            text:'Learn to start building a webpage from scratch. You decide yout own pace, couse and speed.',
          },
          {
            title:'System Administration',
            text:'Learners are encouraged to study the mechanism and structure of system administation.',
          },
          {
            title:'Graphic Design',
            text:'Have a passion for graphics and arts? Show your talents with confidence and self-assertiveness.',
          }
        ]
      }
    }
  }

</script>

<style lang="scss">


  @import "@/styles/general.scss";

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