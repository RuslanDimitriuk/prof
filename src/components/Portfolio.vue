<template>
    <div class="portfolio">
        <div class="portfolio__title">
            <h4 class="portfolio__title-head">PORTFOLIO</h4>
            <span class="portfolio__title-text">WORK I HAVE DONE</span>
        </div>
        <div v-for="item in portfolioProjectData" class="portfolioCardBox" :key="item.id">
            <portfolio-card :project-data="item"/>
        </div>
    </div>
</template>

<script>
    import PortfolioCard from "./PortfolioCard";

    export default {
        name: "Portfolio",
        components: {PortfolioCard},
        data() {
            return {
                portfolioProjectData: [
                    {
                        id: 1,
                        title: 'Title-1',
                        description: 'Descr-1',
                        link: '#'
                    },
                    {
                        id: 2,
                        title: 'Title-2',
                        description: 'Descr-2',
                        link: '#'
                    },
                    {
                        id: 3,
                        title: 'Title-3',
                        description: 'Descr-3',
                        link: '#'
                    }
                ]
            }
        }
    }
</script>

<style scoped>
    .portfolio {

    }

    .portfolioCardBox {
        display: inline-block;
    }

    .portfolio__title {
        padding: 40px 0px;
        text-align: center;
    }

    .portfolio__title-head {
        font-size: 28px;
        margin-bottom: 20px;
    }

    .portfolio__title-text {
        font-size: 32px;
        font-weight: bold;
        margin-bottom: 20px;
    }
</style>