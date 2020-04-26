<template>
  <div class="services" id="services">
    <div class="services__title">
      <h4 class="services__title-head">SERVICES</h4>
      <span class="services__title-text">WHAT I CAN DO</span>
    </div>
    <div class="services__card-box">
      <div v-for="item in servicesData" class="services__card" :key="item.id">
        <services-card :data-service="item"/>
      </div>
    </div>
  </div>
</template>

<script>
  import ServicesCard from "./ServicesCard";

  export default {
    name: "Services",
    components: {ServicesCard},
    data() {
      return {
        servicesData: [
          {
            id: 1,
            img: 'settings-gears',
            title: 'WEB DEVELOPMENT',
            text: 'Full front-end side development cycle using both native JS and Vue.js. Possible implementation of the back-end side using node.js'
          },
          {
            id: 2,
            img: 'smartphone',
            title: 'RESPONSIVE IMPLEMENTATION',
            text: 'Implementation ADW (adaptive web design) и RWD (responsive web design) in all projects'
          },
          {
            id: 3,
            img: 'clock',
            title: 'SUPPORT',
            text: 'Implemented interaction and assistance in the implementation and support of the project'
          }
        ]
      }
    }
  }
</script>

<style scoped>
  .services {

  }

  .services__title {
    padding: 40px 0px;
    text-align: center;
  }

  .services__title-head {
    font-size: 28px;
    margin-bottom: 20px;
  }

  .services__title-text {
    font-size: 32px;
    font-weight: bold;
    margin-bottom: 20px;
  }
  .services__card-box{
    display: flex;
    justify-content: space-around;
  }
  .services__card{
    width: 20%;
  }
  @media screen and (max-width: 900px) {
    .services__card-box{
      flex-direction: column;
    }
    .services__card{
      margin: 0px auto 30px auto;
      width: 80%;
    }
  }
</style>
