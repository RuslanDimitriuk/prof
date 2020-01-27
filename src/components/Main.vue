<template>
    <div>
        <div class="main">
            <div class="main__content">
                <h1 class="main__title">Hi! I'm Ruslan.</h1>
                <div>
                    <span class="main__info">Developer located in Minsk.</span>
                    <div class="container">
                        <div>Coding is <span class="typed-text"></span>
                            <div class="cursor">!</div>
                        </div>
                    </div>
                </div>
            </div>
            <div class="main__arrow-block" @click="wayDown">
                <div class="main__arrow">
                </div>
            </div>
        </div>
        <about-me/>
        <services/>
        <statistics/>
        <portfolio/>
        <feed-back/>
    </div>
</template>

<script>
    import AboutMe from "./AboutMe";
    import Statistics from "./Statistics";
    import Portfolio from "./Portfolio";
    import Services from "./Services";
    import FeedBack from "./FeedBack";

    export default {
        name: "Main",
        components: {FeedBack, Services, Portfolio, Statistics, AboutMe},
        data() {
            return {
                typedTextSpan: null,
                cursorSpan: null,

                textArray: ["hard", "fun", "LIFE"],
                typingDelay: 200,
                erasingDelay: 100,
                newTextDelay: 2000, // Delay between current and next text
                textArrayIndex: 0,
                charIndex: 0
            }
        },
        methods: {
            wayDown() {
                let currentScroll = window.scrollY;
                let wHeight = document.getElementsByClassName('main')[0].clientHeight;
                currentScroll = currentScroll + 5;
                window.scrollTo(pageXOffset, currentScroll);
                setTimeout(() => {
                    if (wHeight > window.scrollY) {
                        this.wayDown();
                    } else {
                        currentScroll = 0;
                    }
                }, 1)
            },
            type() {
                if (this.charIndex < this.textArray[this.textArrayIndex].length) {
                    if (!this.cursorSpan.classList.contains("typing")) this.cursorSpan.classList.add("typing");
                    this.typedTextSpan.textContent += this.textArray[this.textArrayIndex].charAt(this.charIndex);
                    this.charIndex++;
                    setTimeout(this.type, this.typingDelay);
                } else {
                    this.cursorSpan.classList.remove("typing");
                    setTimeout(this.erase, this.newTextDelay);
                }
            },

            erase() {
                if (this.charIndex > 0) {
                    if (!this.cursorSpan.classList.contains("typing")) this.cursorSpan.classList.add("typing");
                    this.typedTextSpan.textContent = this.textArray[this.textArrayIndex].substring(0, this.charIndex - 1);
                    this.charIndex--;
                    setTimeout(this.erase, this.erasingDelay);
                } else {
                    this.cursorSpan.classList.remove("typing");
                    this.textArrayIndex++;
                    if (this.textArrayIndex >= this.textArray.length) this.textArrayIndex = 0;
                    setTimeout(this.type, this.typingDelay + 1100);
                }
            },
        },
        mounted() {
            this.typedTextSpan = document.querySelector(".typed-text");
            this.cursorSpan = document.querySelector(".cursor");
            if (this.textArray.length) setTimeout(this.type, this.newTextDelay + 250);
        }
    }
</script>

<style scoped>
    .main {
        background: url("./../assets/img-main.jpg") no-repeat;
        background-size: cover;
        width: 100%;
        height: 100vh;
        color: #fff;
    }

    .main__arrow-block {
        position: relative;
    }

    .main__arrow {
        cursor: pointer;
        width: 48px;
        height: 48px;
        background: url("./../assets/arrow.png") no-repeat;
        background-size: cover;
        position: absolute;
        left: 20vw;
        animation: bounce 2s infinite;
    }

    @keyframes bounce {
        from {
            top: 0px
        }
        40% {
            top: 40px
        }
        50% {
            top: 35px
        }
        60% {
            top: 40px
        }
        to {
            top: 0px
        }
    }

    .main__title {
        font-size: 88px;
    }

    .main__info {
        font-size: 32px;
    }

    .main__content {
        padding-top: 40vh;
        margin-left: 20%;
        width: 60%;
    }

    .container {
        height: 20vh;
        align-items: center;
        margin-top: 30px;
    }

    .container div {
        font-size: 3rem;
        font-weight: bold;
        letter-spacing: 0.1rem;
        overflow: hidden;
    }

    .container div div.typed-text {
        font-weight: normal;
        color: #fff;
    }

    .container div div.cursor {
        content: '';
        display: inline-block;
        background-color: #fff;
        margin-left: 0.1rem;
        width: 3px;
        animation: blink 1s infinite;
    }

    .container div div.cursor.typing {
        animation: none;
    }

    @keyframes blink {
        0% {
            background-color: #fff;
        }
        49% {
            background-color: #fff;
        }
        50% {
            background-color: transparent;
        }
        99% {
            background-color: transparent;
        }
        100% {
            background-color: #fff;
        }
    }
</style>