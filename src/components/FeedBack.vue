<template>
    <div>
        <div class="feed-back__title">
            <h4 class="feed-back__title-head">CONTACT</h4>
            <span class="feed-back__title-text">GET IN TOUCH</span>
        </div>
        <div class="feed-back__info">
            <div class="feed-back__input-block">
                <div class="feed-back__input-block_b">
                    <input type="text" placeholder="Name" class="feed-back__input" v-model="feedBackInfo.name">
                    <input type="text" placeholder="Email" class="feed-back__input" v-model="feedBackInfo.email">
                </div>
            </div>
            <div class="feed-back__input-text">
                <textarea placeholder="How can I help you?" class="textarea"/>
            </div>
        </div>
        <div class="feed-back__btn-box">
            <button class="feed-back__btn">SEND MESSAGE</button>
        </div>
    </div>
</template>

<script>
    export default {
        name: "FeedBack",
        data() {
            return {
                feedBackInfo: {
                    name: '',
                    email: '',
                    text: ''
                }
            }
        }
    }
</script>

<style scoped>

    .feed-back__title {
        padding: 40px 0px;
        text-align: center;
    }

    .feed-back__title-head {
        font-size: 28px;
        margin-bottom: 20px;
    }

    .feed-back__title-text {
        font-size: 32px;
        font-weight: bold;
        margin-bottom: 20px;
    }

    .feed-back__input-block {
        display: flex;
        justify-content: center;
    }
    .feed-back__input-block_b{
        width: 80%;
        display: flex;
        justify-content: center;
    }
    .feed-back__input {
        text-decoration: none;
        border: none;
        border-bottom: 2px solid #000000;
        height: 40px;
        width: 25%;
        margin: 50px 100px;
        padding-left: 25px;
        font-size: 18px;
    }
    .feed-back__input-text{
        text-align: center;
    }
    .textarea{
        width: calc(50% + 50px);
        height: 150px;
        font-size: 18px;
        border: none;
        border-bottom: 2px solid #000000;
        margin-bottom: 50px;
        resize: none;
        padding-left: 25px;
        padding-right: 25px;
        padding-top: 10px;
    }
    .feed-back__btn-box{
        text-align: center;
        margin-bottom: 80px;
    }
    .feed-back__btn {
        font-size: 16px;
        transition: 300ms;
        width: 160px;
        height: 40px;
        background: #000;
        border: 2px solid #000;
        color: #fff;
    }

    .feed-back__btn:hover {
        background: #fff;
        color: #000;
    }
</style>