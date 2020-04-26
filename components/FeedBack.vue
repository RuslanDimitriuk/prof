<template>
  <div id="feedBack">
    <form action="https://formspree.io/mqkqkqzq"
          method="POST">
      <div class="feed-back__title">
        <h4 class="feed-back__title-head">CONTACT</h4>
        <span class="feed-back__title-text">GET IN TOUCH</span>
      </div>
      <div class="feed-back__info">
        <div class="feed-back__input-block">
          <div class="feed-back__input-block_b">
            <input type="text" @input="onClick('name')" placeholder="Name" class="feed-back__input"
                   :class="{isValidate: !valid.name}" v-model="feedBackInfo.name" required name="Name">
            <input type="email" @input="onClick('email')" placeholder="Email" class="feed-back__input"
                   :class="{isValidate: !valid.email}" v-model="feedBackInfo.email" name="Email" required>
          </div>
        </div>
        <div class="feed-back__input-text">
                    <textarea @input="onClick('text')" placeholder="How can I help you?" class="textarea" name="Message"
                              :class="{isValidate: !valid.text}" v-model="feedBackInfo.text" required/>
        </div>
      </div>
      <div class="feed-back__btn-box">
        <button class="feed-back__btn" type="submit" @click="isValidate">SEND MESSAGE</button>
      </div>
    </form>
  </div>
</template>

<script>
  export default {
    name: "FeedBack",
    data() {
      return {
        valid: {
          name: true,
          email: true,
          text: true
        },
        feedBackInfo: {
          name: '',
          email: '',
          text: ''
        }
      }
    },
    methods: {
      onClick(value) {
        if (value === 'name') {
          this.valid.name = true;
        }
        if (value === 'email') {
          this.valid.email = true;
        }
        if (value === 'text') {
          this.valid.text = true;
        }
      },
      isValidate() {

        if (this.feedBackInfo.name === '' || this.feedBackInfo.name === null) {
          this.valid.name = false;
        } else {
          this.valid.name = true;
        }

        if (this.feedBackInfo.email === '' || this.feedBackInfo.email === null) {
          this.valid.email = false;
        } else {
          this.valid.email = true;
        }

        if (this.feedBackInfo.text === '' || this.feedBackInfo.text === null) {
          this.valid.text = false;
        } else {
          this.valid.text = true;
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

  .feed-back__input-block_b {
    width: 60%;
    display: flex;
    justify-content: space-between;
  }

  .feed-back__input {
    text-decoration: none;
    border: none;
    border-bottom: 2px solid #000000;
    height: 40px;
    width: 40%;
    margin: 50px 0px;
    padding-left: 25px;
    font-size: 18px;
    outline: none
  }

  .isValidate {
    border-bottom: 2px solid #ff0311 !important;
  }

  .feed-back__input-text {
    text-align: center;
  }

  .textarea {
    box-sizing: border-box;
    width: 60%;
    height: 150px;
    font-size: 18px;
    border: none;
    border-bottom: 2px solid #000000;
    margin-bottom: 50px;
    resize: none;
    padding-top: 10px;
    outline: none;
    padding-left: 25px;
    padding-right: 25px;
  }

  .feed-back__btn-box {
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
  @media screen and (max-width: 900px) {
    .feed-back__input-block_b {
      width: 60%;
      display: flex;
      flex-direction: column;
    }
    .feed-back__input {
      width: 100%;
      margin: 30px 0px;
    }
  }
</style>
