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
      <h1>
        <span>Hello, I'm Nazar</span>
        <span class="typed-text"></span>
        <span class="cursor">&nbsp;</span>
      </h1>
    </div>
  </div>
</template>

<script>
export default {
  name: "home",
  components: {},
  data: () => ({
    txt: "",
    words: ["Software Engineer", "Front End Developer"]
  })
};
</script>

<style lang="scss" scoped>
.wrapper {
  position: absolute;
  // display: flex;
  // width: 100%;
  // height: 100vh;
  justify-content: center;
  align-items: center;
  top: 50%;
  left: 50%;
  text-align: center;
  transform: translate(-50%, -50%);
  h1 {
    font-size: 4rem;
    font-weight: normal;
    span.typed-text {
      color: #d2b94b;
    }
    span.cursor {
      display: inline-block;
      margin-left: 3px;
      width: 4px;
      height: 4rem;
      background-color: #000;
      // animation: cursorBlink ease 1s infinite;
    }
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
    // animation-delay: 1s;
  }
  &:nth-child(3) {
    width: 35px;
    height: 35px;
    left: 30%;
    background-image: url("/bg_img/X.png");
    animation-duration: 9s;
    // animation-delay: 2s;
  }
  &:nth-child(4) {
    width: 15px;
    height: 15px;
    left: 40%;
    background-image: url("/bg_img/S.png");
    animation-duration: 6s;
    // animation-delay: 0s;
  }
  &:nth-child(5) {
    width: 30px;
    height: 30px;
    left: 50%;
    background-image: url("/bg_img/A.png");
    animation-duration: 10s;
    // animation-delay: 1s;
  }
  &:nth-child(6) {
    width: 20px;
    height: 20px;
    left: 60%;
    background-image: url("/bg_img/0.png");
    animation-duration: 7s;
    // animation-delay: 3s;
  }
  &:nth-child(7) {
    width: 10px;
    height: 10px;
    left: 70%;
    background-image: url("/bg_img/X.png");
    animation-duration: 9s;
    // animation-delay: 2s;
  }
  &:nth-child(8) {
    width: 25px;
    height: 25px;
    left: 80%;
    background-image: url("/bg_img/S.png");
    animation-duration: 6s;
    // animation-delay: 1s;
  }
  &:nth-child(9) {
    width: 15px;
    height: 15px;
    left: 90%;
    background-image: url("/bg_img/A.png");
    animation-duration: 10s;
    // animation-delay: 0s;
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
  0%,
  100% {
    opacity: 0;
  }
  50% {
    opacity: 1;
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
