<template>
    <div class="statistics">
        <div class="statistics__data">
            <div>
                <div class="statistics__data-img">
                    <img src="./../assets/labes/smile.png" width="32" height="32" class="img">
                </div>
                <div>
                    <div class="statistics__data-number">10</div>
                    <div class="statistics__data-text">Happy Clients</div>
                </div>
            </div>
            <div>
                <div class="statistics__data-img">
                    <img src="./../assets/labes/like.png" width="32" height="32" class="img">
                </div>
                <div>
                    <div class="statistics__data-number">3</div>
                    <div class="statistics__data-text">Projects Completed</div>
                </div>
            </div>
            <div>
                <div class="statistics__data-img">
                    <img src="./../assets/labes/sad.png" width="32" height="32" class="img">
                </div>
                <div class="statistics__data-info">
                    <div class="statistics__data-number">0</div>
                    <div class="statistics__data-text">Sad Clients</div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        name: "Statistics"
    }
</script>

<style scoped>
    .statistics {
        background-image: url("./../assets/road.jpg");
        background-size: cover;
        background-repeat: no-repeat;
        background-position: center;
        background-attachment: fixed;
        position: relative;
        overflow: hidden;
    }

    .statistics__data {
        color: #fff;
        padding: 150px 0 150px 0;
        display: flex;
        justify-content: space-around;
        background: rgba(0,0,0, .3);
    }
    .statistics__data-img{
        width: 64px;
        height: 64px;
        display: flex;
        border-radius: 32px;
        flex-direction: column;
        justify-content: center;
        background: rgba(255,255,255, .8);
        margin: 0px auto 30px auto;
    }
    .img{
        margin: 0px auto;
    }
    .statistics__data-number{
        text-align: center;
        font-size: 24px;
        font-weight: bold;
        margin-bottom: 20px;
    }
    .statistics__data-text{
        text-align: center;
        font-size: 24px;
    }
</style>