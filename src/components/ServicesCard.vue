<template>
    <div class="services-card">
        <div class="services-card__img">
            <img :src="getImage" height="32" width="32">
        </div>
        <div class="services-card__info">
            <h4 class="services-card__info-title">{{dataService.title}}</h4>
            <div>
                {{dataService.text}}
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        name: "ServicesCard",
        data () {
            return {

            }
        },
        props: {
            dataService: {
                type: Object
            }
        },
        computed: {
            getImage() {
                return require(`./../assets/labes/${this.dataService.img}.png`);
            }
        },
    }
</script>

<style scoped>
    .services-card{
        padding-bottom: 100px;
    }
    .services-card__img{
        text-align: center;
        margin-bottom: 20px;
    }
    .services-card__info{
        text-align: center;
    }
    .services-card__info-title{
        font-weight: bold;
        margin-bottom: 20px;
    }
</style>