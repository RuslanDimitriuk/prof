<template>
  <div class="about-me" id="aboutMe">
    <div class="about-me__content">
      <div class="about-me__photo"></div>
      <div class="about-me__info">
        <h3 class="about-me__title">ABOUT ME.</h3>
        <span class="about-me__prof">Web Developer</span>
        <div>
          <p class="about-me__info-text">My name is Ruslan Dimitryuk. I am a front-end developer.
            I have experience developing using native JS and modern reactive frameworks. There is experience
            in implementing multifunctional web applications built on the principle of SPA, static sites and
            online stores, implementing animations of varying complexity using CSS, canvas, SVG. The main
            working framework is vue.js</p>
          <p class="about-me__info-text">I strive to keep up with modern development technologies, therefore I
            always study and implement new approaches and methodologies for the development of highly loaded
            and high-quality software. I am in excellent contact with the development team and try to bring
            new and better development solutions to the teamwork.</p>
        </div>
        <div class="about-me__social">
          <div style="display: flex; justify-content: center">
            <a href="https://www.linkedin.com/in/ruslandimitriuk/" target="_blank">
              <div class="circle">
                <div class="bg-linkidin"></div>
              </div>
            </a>
          </div>
          <div style="display: flex; justify-content: center">
            <a href="https://twitter.com/Ruslan06214589" target="_blank">
              <div class="circle">
                <div class="bg-twitter"></div>
              </div>
            </a>
          </div>
          <div style="display: flex; justify-content: center"><a
            href="https://www.instagram.com/ruslandimitriuk/">
            <div class="circle">
              <div class="bg-insta"></div>
            </div>
          </a></div>
          <div style="display: flex; justify-content: center"><a href="mailto:ruslandimitriuk@gmail.com">
            <div class="circle">
              <div class="bg-mail"></div>
            </div>
          </a></div>
        </div>
        <div class="link-box"><a href="https://RuslanDimitriuk.github.io/CV_Front-end-dev_Dimitriuk.pdf" download="" class="about-me__btn">DOWNLOAD CV</a></div>
      </div>
    </div>
  </div>
</template>

<script>
  export default {
    name: "AboutMe"
  }
</script>

<style scoped>
  .about-me {
    padding: 150px 0 150px 0;
  }

  .about-me__content {
    display: flex;
    width: 70%;
    margin: 0px auto;
  }

  .about-me__photo {
    width: 400px;
    height: 400px;
    background: url("./../static/I.jpg") no-repeat;
    background-size: cover;
  }

  .about-me__info {
    width: calc(100% - 440px);
    margin: 10px 20px 10px 20px;
  }

  .about-me__title {
    font-size: 32px;
    margin-bottom: 10px;
  }

  .about-me__prof {
    display: inline-block;
    font-size: 22px;
    margin-bottom: 15px;
  }

  .about-me__info-text {
    font-size: 18px;
    line-height: 24px;
    margin-bottom: 15px;
  }

  .about-me__btn {
    display: flex;
    flex-direction: column;
    justify-content: center;
    text-decoration: none;
    text-align: center;
    font-size: 16px;
    transition: 300ms;
    width: 160px;
    height: 40px;
    background: #000;
    border: 2px solid #000;
    color: #fff;
  }

  .about-me__btn:hover {
    background: #fff;
    color: #000;
  }

  .about-me__social {
    margin-bottom: 15px;
    display: flex;
    justify-content: space-around;
    width: 40%;
    min-width: 240px;
  }

  .circle {
    width: 50px;
    height: 50px;
    background: #fff;
    -moz-border-radius: 30px;
    -webkit-border-radius: 30px;
    border-radius: 30px;
    border: solid 2px #000;
    display: flex;
    justify-content: center;
  }

  .circle:hover {
    transition: 300ms;
    transform: scale(1.1);
    background: #cbe5f3;
  }

  .bg-linkidin {
    margin-top: 8px;
    width: 32px;
    height: 32px;
    background: url('../static/social_sprites.png') -20px -20px;
  }

  .bg-skype {
    margin: auto 0px;
    width: 32px;
    height: 32px;
    background: url('../static/social_sprites.png') -92px -20px;
  }

  .bg-twitter {
    margin: auto 0px;
    width: 32px;
    height: 32px;
    background: url('../static/social_sprites.png') -20px -92px;
  }

  .bg-insta {
    margin: auto 0px;
    width: 32px;
    height: 32px;
    background: url('../static/social_sprites.png') -92px -92px;
  }

  .bg-mail {
    margin: auto 0px;
    width: 32px;
    height: 32px;
    background: url('../static/social_sprites.png') -164px -20px;
  }

  @media screen and (max-width: 1200px) {
    .about-me {
      padding: 50px 0 50px 0;
    }

    .about-me__content {
      display: flex;
      flex-direction: column;
      width: 100%;
    }

    .about-me__photo {
      width: 80vw;
      height: 80vw;
      margin: 0px auto 50px auto;
    }

    .about-me__info {
      width: 80%;
      text-align: center;
      margin: 0px auto 50px auto;
    }

    .about-me__title {
      text-align: center;
    }

    .about-me__prof {
      display: block;
      text-align: center;
    }

    .about-me__info-text {
      text-align: left;
    }

    .about-me__social {
      margin: 30px auto;

    }
    .link-box{
      display: flex;
      justify-content: center;
    }
  }
</style>
