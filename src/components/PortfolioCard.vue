<template>
    <div class="card">
        <div class="card__main">
            <a :href="projectData.link" target="_blank">
                <div class="card__main-block">
                    <h4 class="card__main-title">{{projectData.title}}</h4>
                    <span class="card__main-description">{{projectData.description}}</span>
                </div>
            </a>
        </div>
        <div>

        </div>
    </div>
</template>

<script>
    export default {
        name: "PartfolioCard",
        data() {
            return {}
        },
        props: {
            projectData: {
                type: Object
            }
        }
    }
</script>

<style scoped>
    .card {
        position: relative;
        width: 25vw;
        height: 25vw;
        margin: calc(8vw / 2);
        background: url("./../assets/img-main.jpg") no-repeat;
        background-size: auto;
        display: flex;
        justify-content: center;
    }

    .card:hover .card__main {
        display: block;
        animation: block 500ms forwards;
    }

    .card__main {
        position: absolute;
        top: 1vw;
        left: 1vw;
        width: 23vw;
        height: 23vw;
        background: rgba(255, 255, 255, .6);
        margin: auto 0px;
        display: none;
        border-radius: 3px;
        cursor: pointer;
        text-align: center;
    }

    @keyframes block {
        from {
            top: 6vw;
            left: 6vw;
            width: 13vw;
            height: 13vw;
            background: rgba(255, 255, 255, .0);
        }
        to {
            top: 1vw;
            left: 1vw;
            width: 23vw;
            height: 23vw;
            background: rgba(255, 255, 255, .6);
        }

    }

    .card__main-block {
        height: 100%;
        display: flex;
        flex-direction: column;
        justify-content: center;
    }

    .card__main-title {
        margin-bottom: 30px;
    }

    .card__main-description {

    }
</style>