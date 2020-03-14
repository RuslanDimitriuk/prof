<template>
    <div class="portfolio" id="portfolio">
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
                        title: 'ATU and TU',
                        description: 'Corporate WEB application for registration, examination, creation and modification of administrative territorial units, as well as for displaying spatial information and conducting its measurements.',
                        link: 'http://ate-te.nca.by',
                        class: 'ate'
                    },
                    {
                        id: 2,
                        title: 'RA',
                        description: 'Corporate web application for maintaining a unified register of appraisers and a register of appraisal reports',
                        link: 'http://ro.nca.by',
                        class: 'ro'
                    },
                    {
                        id: 3,
                        title: 'FARO MEBEL',
                        description: 'Furniture online store in St. Petersburg',
                        link: 'http://faromebel.ru',
                        class: 'faro'
                    }
                ]
            }
        }
    }
</script>

<style scoped>
    .portfolio {
background: #d5d5d5;
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
    @media screen and (max-width: 900px) {
        .portfolioCardBox {
            display: flex;
            flex-direction: column;
        }
    }
</style>