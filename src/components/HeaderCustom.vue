<template>
    <div>
        <div :class="{header_w: isScroll, header: !isScroll}">
            <div class="header__element header__logo">
                <div class="logo"></div>
            </div>
            <div class="header__element">
                <ul class="header__nav">
                    <li class="header__nav-elem"><a class="header__nav-elem-link"
                                                    :class="{active: isTrue, element_w: isScroll}" href="#">HOME</a>
                    </li>
                    <li class="header__nav-elem"><a class="header__nav-elem-link"
                                                    :class="{active: isTrue, element_w: isScroll}" href="#">ABOUT</a>
                    </li>
                    <li class="header__nav-elem"><a class="header__nav-elem-link"
                                                    :class="{active: isTrue, element_w: isScroll}" href="#">SERVICES</a>
                    </li>
                    <li class="header__nav-elem"><a class="header__nav-elem-link"
                                                    :class="{active: isTrue, element_w: isScroll}" href="#">WORKS</a>
                    </li>
                    <li class="header__nav-elem"><a class="header__nav-elem-link"
                                                    :class="{active: isTrue, element_w: isScroll}" href="#">CONTACT</a>
                    </li>
                </ul>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        name: 'HelloWorld',
        data() {
            return {
                isScroll: false,
                isTrue: true
            }
        },
        props: {
            msg: String
        },
        methods: {
            isScrollY() {
                if (window.scrollY > 100) {
                    this.isScroll = true;
                } else {
                    this.isScroll = false;
                }
            }
        },
        mounted() {
            window.addEventListener('scroll', this.isScrollY);
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
        background: rgba(255,255,255, .8);
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
        background: url("./../assets/logo.png") no-repeat;
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
</style>
