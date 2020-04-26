<template>
  <div class="footer">
    <div class="footer__content-box">
      <div class="footer__info">
        <div class="footer__info-elem">
          <span class="footer__info-elem-title">Email</span>
          <a class="footer__info-elem-info"
             href="mailto:ruslandimitriuk@gmail.com">ruslandimitriuk@gmail.com</a>
        </div>
        <div class="footer__info-elem">
          <span class="footer__info-elem-title">Phone No.</span>
          <a class="footer__info-elem-info" href="tel:+375445467997">+375 44 546-79-97</a>
        </div>
        <div class="footer__info-elem">
          <span class="footer__info-elem-title">City</span>
          <a class="footer__info-elem-info" target="_blank"
             href="https://goo.gl/maps/aaUPk53kHWGnLtMn7">Minsk</a>
        </div>
      </div>
      <div class="footer__my">
        <span>Ruslan © 2020. All Right Reserved.</span>
      </div>

    </div>
  </div>
</template>

<script>
  export default {
    name: "FooterCustom"
  }
</script>

<style scoped>
  .footer {
    color: #fff;
    background: #000;
    display: flex;
    justify-content: center;
  }

  .footer__content-box {
    width: 80%;
  }

  .footer__info {
    display: flex;
    justify-content: space-around;
    margin-top: 30px;
    padding-bottom: 20px;
    border-bottom: solid 2px #b4d1df;
  }

  .footer__my {
    margin-top: 30px;
    margin-bottom: 30px;
    font-size: 12px;
    display: flex;
    justify-content: center;
  }

  .footer__info-elem {
    text-align: center;
    width: 300px;
  }

  .footer__info-elem-title {
    display: block;
    text-transform: uppercase;
    text-align: center;
    margin-bottom: 15px;
  }

  .footer__info-elem-info {
    text-decoration: none;
    color: #fff
  }
  @media screen and (max-width: 900px){
    .footer__info {
      flex-direction: column;
    }
    .footer__info-elem {
      text-align: center;
      width: 80%;
      margin: 0px auto 30px auto;
    }
  }
</style>
