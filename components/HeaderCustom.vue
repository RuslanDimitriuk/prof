<template>
  <div>
    <div :class="{header_w: isScroll, header: !isScroll}">
      <div class="header__element header__logo">
        <div class="logo"></div>
      </div>
      <div class="header__element">
        <ul class="header__nav" :class="{activeManu: isActiveMenu, activeManu_w: isScroll}">
          <li class="header__nav-elem"><a class="header__nav-elem-link" @click="clickElementMenu"
                                          :class="{active: isMain, element_w: isScroll}" href="#main">HOME</a>
          </li>
          <li class="header__nav-elem"><a class="header__nav-elem-link" @click="clickElementMenu"
                                          :class="{active: isAboutMe, element_w: isScroll}" href="#aboutMe">ABOUT</a>
          </li>
          <li class="header__nav-elem"><a class="header__nav-elem-link" @click="clickElementMenu"
                                          :class="{active: isServices, element_w: isScroll}" href="#services">SERVICES</a>
          </li>
          <li class="header__nav-elem"><a class="header__nav-elem-link" @click="clickElementMenu"
                                          :class="{active: isWorks, element_w: isScroll}" href="#portfolio">WORKS</a>
          </li>
          <li class="header__nav-elem"><a class="header__nav-elem-link" @click="clickElementMenu"
                                          :class="{active: isContact, element_w: isScroll}" href="#feedBack">CONTACT</a>
          </li>
        </ul>
        <svg class="ham ham3" viewBox="0 0 100 100" width="80" onclick="this.classList.toggle('active')"
             @click="onClickHam" ref="ham">
          <path
            class="line top" :class="{line_w: isScroll}"
            d="m 70,33 h -40 c -11.092231,0 11.883874,13.496726 -3.420361,12.956839 -0.962502,-2.089471 -2.222071,-3.282996 -4.545687,-3.282996 -2.323616,0 -5.113897,2.622752 -5.113897,7.071068 0,4.448316 2.080609,7.007933 5.555839,7.007933 2.401943,0 2.96769,-1.283974 4.166879,-3.282995 2.209342,0.273823 4.031294,1.642466 5.857227,-0.252538 v -13.005715 16.288404 h 7.653568"/>
          <path
            class="line middle" :class="{line_w: isScroll}"
            d="m 70,50 h -40 c -5.6862,0 -8.534259,5.373483 -8.534259,11.551069 0,7.187738 3.499166,10.922274 13.131984,10.922274 11.021777,0 7.022787,-15.773343 15.531095,-15.773343 3.268142,0 5.177031,-2.159429 5.177031,-6.7 0,-4.540571 -1.766442,-7.33533 -5.087851,-7.326157 -3.321409,0.0092 -5.771288,2.789632 -5.771288,7.326157 0,4.536525 2.478983,6.805271 5.771288,6.7"/>
          <path
            class="line bottom" :class="{line_w: isScroll}"
            d="m 70,67 h -40 c 0,0 -3.680675,0.737051 -3.660714,-3.517857 0.02541,-5.415597 3.391687,-10.357143 10.982142,-10.357143 4.048418,0 17.88928,0.178572 23.482143,0.178572 0,2.563604 2.451177,3.403635 4.642857,3.392857 2.19168,-0.01078 4.373905,-1.369814 4.375,-3.392857 0.0011,-2.023043 -1.924401,-2.589191 -4.553571,-4.107143 -2.62917,-1.517952 -4.196429,-1.799562 -4.196429,-3.660714 0,-1.861153 2.442181,-3.118811 4.196429,-3.035715 1.754248,0.0831 4.375,0.890841 4.375,3.125 2.628634,0 6.160714,0.267857 6.160714,0.267857 l -0.178571,-2.946428 10.178571,0 -10.178571,0 v 6.696428 l 8.928571,0 -8.928571,0 v 7.142858 l 10.178571,0 -10.178571,0"/>
        </svg>
      </div>
    </div>
  </div>
</template>

<script>
  export default {
    name: 'HelloWorld',
    data() {
      return {
        isActiveMenu: false,
        isScroll: false,
        isTrue: true,
        stMain: null,
        stAboutMe: null,
        stServices: null,
        stWorks: null,
        stContacts: null,
        currentScrollY: null,
        isMain: true,
        isAboutMe: false,
        isServices: false,
        isWorks: false,
        isContact: false,
      }
    },
    props: {
      msg: String
    },
    computed: {},
    methods: {
      isScrollY() {
        if (window.scrollY > 100) {
          this.isScroll = true;
        } else {
          this.isScroll = false;
        }
        this.currentScrollY = window.scrollY;
      },
      onClickHam() {
        this.isActiveMenu = !this.isActiveMenu;
      },
      clickElementMenu() {
        this.isActiveMenu = false;
        this.$refs.ham.classList.toggle('active');
      }
    },
    watch: {
      currentScrollY: {
        handler: function (val, oldVal) {
          // console.log(val, this.stAboutMe, window.scrollY);
          if (this.stAboutMe > window.scrollY + 200) {
            this.isMain = true;
          } else {
            this.isMain = false;
          }

          if (this.stServices > window.scrollY + 200 && this.stAboutMe < window.scrollY + 200) {
            this.isAboutMe = true;
          } else {
            this.isAboutMe = false;
          }

          if (this.stWorks > window.scrollY + 200 && this.stServices < window.scrollY + 200) {
            this.isServices = true;
          } else {
            this.isServices = false;
          }

          if (this.stContacts > window.scrollY + 300 && this.stWorks < window.scrollY + 200) {
            this.isWorks = true;
          } else {
            this.isWorks = false;
          }

          if (this.stContacts < window.scrollY + 300) {
            this.isContact = true;
          } else {
            this.isContact = false;
          }
        },
        deep: true
      }

    },
    mounted() {
      window.addEventListener('scroll', this.isScrollY);

      this.stMain = document.getElementById('main').getBoundingClientRect().y + window.pageYOffset;
      this.stAboutMe = document.getElementById('aboutMe').getBoundingClientRect().y + window.pageYOffset;
      this.stServices = document.getElementById('services').getBoundingClientRect().y + window.pageYOffset;
      this.stWorks = document.getElementById('portfolio').getBoundingClientRect().y + window.pageYOffset;
      this.stContacts = document.getElementById('feedBack').getBoundingClientRect().y + window.pageYOffset;
    }
  }
</script>

<style scoped>
  .header {
    transition: 1s;
    position: fixed;
    top: 0px;
    width: 100%;
    display: flex;
    height: 100px;
    z-index: 100;
  }

  .header_w {
    position: fixed;
    top: 0px;
    width: 100%;
    display: flex;
    height: 110px;
    z-index: 100;
    transition: 1s;
    background: rgba(255, 255, 255, .8);
  }

  .element_w {
    transition: 1s;
    color: #000 !important;
  }

  .element_w::before {
    transition: 1s;
    background-color: #000 !important;
  }


  .header__element {
    width: 50%;
    margin: auto 0px;
  }

  .header__logo {
    display: flex;
    justify-content: center;
  }

  .logo {
    width: 80px;
    height: 80px;
    background: url("./../static/logo.png") no-repeat;
    background-size: cover;
    border-radius: 3px;
    cursor: pointer;
  }

  .header__nav {
    width: 60%;
    display: flex;
    justify-content: space-around;
  }

  .header__nav-elem {

  }

  .header__nav-elem-link {
    color: #fff;
    text-decoration: none;
    position: relative;
  }

  .header__nav-elem-link::before {
    content: "";
    position: absolute;
    width: 100%;
    height: 2px;
    bottom: -2px;
    left: 0;
    background-color: #fff;
    visibility: hidden;
    -webkit-transform: scaleX(0);
    -ms-transform: scaleX(0);
    transform: scaleX(0);
    -webkit-transition: all 0.3s ease-in-out 0s;
    -o-transition: all 0.3s ease-in-out 0s;
    transition: all 0.3s ease-in-out 0s
  }

  .active::before {
    visibility: visible;
    transform: scaleX(1);
  }

  .ham {
    display: none;
    cursor: pointer;
    -webkit-tap-highlight-color: transparent;
    transition: transform 400ms;
    padding-right: 20px;
    float: right;
    -moz-user-select: none;
    -webkit-user-select: none;
    -ms-user-select: none;
    user-select: none;
  }

  .line {
    fill: none;
    transition: stroke-dasharray 400ms, stroke-dashoffset 400ms;
    stroke: #fff;
    stroke-width: 5.5;
    stroke-linecap: round;
  }

  .line_w {
    transition: 400ms;
    stroke: #000;
  }

  .ham3 .top {
    stroke-dasharray: 40 130;
  }

  .ham3 .middle {
    stroke-dasharray: 40 140;
  }

  .ham3 .bottom {
    stroke-dasharray: 40 205;
  }

  .ham3.active .top {
    stroke-dasharray: 75 130;
    stroke-dashoffset: -63px;
  }

  .ham3.active .middle {
    stroke-dashoffset: -102px;
  }

  .ham3.active .bottom {
    stroke-dasharray: 110 205;
    stroke-dashoffset: -86px;
  }

  @media screen and (max-width: 1200px) {
    .ham {
      display: block;
    }

    .header {
      height: 70px;
    }

    .header_w {
      height: 80px;
    }

    .header__logo {
      display: none;
    }

    .header__element {
      width: 100%;
    }

    .header__nav {
      display: inline-block;
      flex-direction: column;
      transition: 1s;
      position: absolute;
      height: auto;
      top: 70px;
      right: -100%;
      width: 100%;
      box-sizing: border-box;
    }

    .activeManu {
      flex-direction: column;
      transition: 1s;
      position: absolute;
      top: 70px;
      right: 0px;
      width: 100%;
      display: inline-block;
      background: rgba(255, 255, 255, 0);
    }

    .activeManu_w {
      transition: 1s;
      top: 80px;
      background: rgba(255, 255, 255, .8);
    }

    .header__nav-elem {
      text-align: center;
      margin: 20px 0px;
    }
  }
</style>
