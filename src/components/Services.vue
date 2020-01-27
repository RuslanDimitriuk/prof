<template>
    <div class="services">
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
                        text: 'Lorem Ipsum is simply dummy text of the Lorem has been the industry\'s standard dummy text ever.'
                    },
                    {
                        id: 2,
                        img: 'smartphone',
                        title: 'RESPONSIVE IMPLEMENTATION',
                        text: 'Lorem Ipsum is simply dummy text of the Lorem has been the industry\'s standard dummy text ever.'
                    },
                    {
                        id: 3,
                        img: 'clock',
                        title: 'SUPPORT',
                        text: 'Lorem Ipsum is simply dummy text of the Lorem has been the industry\'s standard dummy text ever.'
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
</style>