<template>
  <div class="home shapes">
    <div class="shape"></div>
    <div class="shape"></div>
    <div class="shape"></div>
    <div class="shape"></div>
    <div class="shape"></div>
    <div class="shape"></div>
    <div class="shape"></div>
    <div class="shape"></div>
    <div class="shape"></div>
    <div class="shape"></div>
    <div class="wrapper">
      <h1>Hello, I'm Nazar</h1>
      <p>
        <span class="typed-text"> {{ typeValue }} </span>
        <span class="cursor" :class="{ typing: typeStatus }">&nbsp; </span>
      </p>
    </div>
  </div>
</template>

<script>
export default {
  name: "home",
  components: {},
  data: () => ({
    typeValue: "",
    typeStatus: false,
    typeWords: [
      "<Software Engineer/>",
      "<Front End Developer/>",
      "<HTML Coder/>"
    ],
    typingSpeed: 200,
    erasingSpeed: 100,
    newTextDelay: 2000,
    typeWordsIndex: 0,
    charIndex: 0
  }),
  methods: {
    typeText() {
      if (this.charIndex < this.typeWords[this.typeWordsIndex].length) {
        if (!this.typeStatus) {
          this.typeStatus = true;
        }
        this.typeValue += this.typeWords[this.typeWordsIndex].charAt(
          this.charIndex
        );
        this.charIndex += 1;
        setTimeout(this.typeText, this.typingSpeed);
      } else {
        this.typeStatus = false;
        setTimeout(this.eraseText, this.newTextDelay);
      }
    },
    eraseText() {
      if (this.charIndex > 0) {
        if (!this.typeStatus) this.typeStatus = true;

        this.typeValue = this.typeWords[this.typeWordsIndex].substring(
          0,
          this.charIndex - 1
        );
        this.charIndex -= 1;
        setTimeout(this.eraseText, this.erasingSpeed);
      } else {
        this.typeStatus = false;
        this.typeWordsIndex += 1;
        if (this.typeWordsIndex >= this.typeWords.length)
          this.typeWordsIndex = 0;
        setTimeout(this.typeText, this.typingSpeed + 1000);
      }
    }
  },
  created() {
    this.$emit("HomePage");
    setTimeout(this.typeText, this.newTextDelay + 200);
  }
};
</script>

<style lang="scss" scoped>
.wrapper {
  position: absolute;
  top: 50%;
  left: 50%;
  text-align: center;
  transform: translate(-50%, -50%);
  color: #303a52;
  font-family: "Raleway", sans-serif;

  h1 {
    font-weight: 700;
    font-size: 4rem;
    letter-spacing: 0.1rem;
  }
  p {
    color: #303a52;
    font-weight: 300;
    font-style: italic;
    letter-spacing: -0.1rem;

    font-size: 2.5rem;
  }
  span.typed-text {
    color: #1e1e1e;
  }
  span.cursor {
    display: inline-block;
    width: 4px;
    height: 2.5rem;
    margin-left: -7px;
    margin-bottom: -6px;
    background-color: #000;
    animation: cursorBlink 1s infinite;
  }
  span.cursor.typing {
    animation: none;
  }
}

.home.shapes {
  position: absolute;
  top: 0;
  left: 0;
  overflow: hidden;
  width: 100%;
  height: 100%;
  z-index: 0;
}
.shapes .shape {
  position: absolute;
  bottom: 0;
  background-repeat: no-repeat;
  background-size: contain;
  animation: fly 10s infinite ease-in;

  &:nth-child(1) {
    width: 35px;
    height: 35px;
    left: 10%;
    background-image: url("/bg_img/A.png");
    animation-duration: 10s;
  }
  &:nth-child(2) {
    width: 10px;
    height: 10px;
    left: 20%;
    background-image: url("/bg_img/0.png");
    animation-duration: 7s;
  }
  &:nth-child(3) {
    width: 35px;
    height: 35px;
    left: 30%;
    background-image: url("/bg_img/X.png");
    animation-duration: 9s;
  }
  &:nth-child(4) {
    width: 15px;
    height: 15px;
    left: 40%;
    background-image: url("/bg_img/S.png");
    animation-duration: 6s;
  }
  &:nth-child(5) {
    width: 30px;
    height: 30px;
    left: 50%;
    background-image: url("/bg_img/A.png");
    animation-duration: 10s;
  }
  &:nth-child(6) {
    width: 20px;
    height: 20px;
    left: 60%;
    background-image: url("/bg_img/0.png");
    animation-duration: 7s;
  }
  &:nth-child(7) {
    width: 10px;
    height: 10px;
    left: 70%;
    background-image: url("/bg_img/X.png");
    animation-duration: 9s;
  }
  &:nth-child(8) {
    width: 25px;
    height: 25px;
    left: 80%;
    background-image: url("/bg_img/S.png");
    animation-duration: 6s;
  }
  &:nth-child(9) {
    width: 15px;
    height: 15px;
    left: 90%;
    background-image: url("/bg_img/A.png");
    animation-duration: 10s;
  }
  &:nth-child(10) {
    width: 30px;
    height: 30px;
    left: 95%;
    background-image: url("/bg_img/0.png");
    animation-duration: 7s;
  }
}

//-->> Start Animations -->>//
@keyframes cursorBlink {
  49% {
    background-color: #000;
  }
  50% {
    background-color: transparent;
  }
  99% {
    background-color: transparent;
  }
}

@keyframes fly {
  0% {
    bottom: -100px;
    transform: translateX(0);
  }
  50% {
    transform: translateX(100px);
  }

  100% {
    bottom: 1080px;
    transform: translateX(-200px);
  }
}
//<<--  End Animations <<--//
</style>
