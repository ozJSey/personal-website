<template>
  <section
    ref="sideSection"
    @click="enlarge"
    class="some-text animated"
  >
    <h1>Özgür Seyidoğlu</h1>
    <p>I am a frontend development focused engineer, from Istanbul, Turkey.</p>
    <p>I am doing professional & production level software for more than 4 years, including working 2 jobs and my freelance experience, more than 5 years.</p>
    <p>Before programming I had been a teacher for almost 2 years teaching physics, mathematics and grammar in English. Currently learning backend, aiming to be full- stack. I've had work experiences in cooperates, semi-government
      establishment, a startup, an IT team, agencies and classrooms 😊 .</p>
    <div
      :class="{opacity: extended}"
      class="side-title"
    >
      <p> More information!</p>
    </div>
  </section>
</template>

<script>
export default {
  data () {
    return {
      extended: false
    }
  },
  methods: {
    enlarge () {
      if (this.extended == false) {
        this.$refs.sideSection.style.right = 0;
        this.$refs.sideSection.classList = 'some-text';
        this.extended = true;
        let fatherDiv = document.querySelector('.some-text');
        fatherDiv.children.forEach((el) => {
          el.classList = "reveal";
        });
      }
      else {
        this.$refs.sideSection.style.right = "95vw";
        this.$refs.sideSection.classList = 'some-text animated';
        this.extended = false;
        let fatherDiv = document.querySelector('.some-text');
        fatherDiv.children.forEach((el) => {
          el.classList = "";
        });
      }
    }
  }
}
</script>

<style lang="scss">
@mixin mobile {
  @media (max-width: 992px) {
    @content;
  }
}
.some-text {
  position: absolute;
  top: 50px;
  width: 100vw;
  border-radius: 0;
  transition: right 0.4s ease-in;
  right: 95vw;
  cursor: pointer;
  background-color: #121314;
  background-image: linear-gradient(
    to right,
    transparent 33%,
    rgba(255, 255, 255, 0.3) 50%,
    transparent 66%
  );
  background-size: 300% 100%;
  animation: shine 1s 2;
  box-shadow: 2px 2px 17px 10px rgba(0, 0, 0, 0.96);
  min-height: 290px;
  &.animated {
    animation: shakeItUpBebegim 4s normal 0s infinite ease-in;
    border-radius: 15px;
  }

  color: #d8d7ed;
  h1,
  p {
    text-align: center;
  }
  p {
    opacity: 0;
    padding: 0 70px;
    @include mobile {
      padding: 0 20px;
    }
  }
  h1 {
    opacity: 0;
    margin-top: 40px;
  }
  h1.reveal {
    animation: revealText 0.6s 0.12s 1 ease-in forwards;
  }
  p.reveal {
    animation: revealText 0.6s 1.15s 1 ease-in forwards;
  }
  .side-title {
    position: absolute;
    right: -140px;
    top: 97px;
    cursor: pointer;
    transition: opacity 0.4s ease-out;
    opacity: 1;
    &.opacity {
      opacity: 0;
    }
    p {
      transform: rotate(90deg);
      font-size: 26px;
      opacity: 1;
    }
  }
}
@keyframes shakeItUpBebegim {
  0% {
    transform: translateX(0px);
  }
  25% {
    transform: translateX(-2px);
  }
  50% {
    transform: translateX(5px);
  }
  80% {
    transform: translateX(-5px);
  }
  100% {
    transform: translateX(0px);
  }
}
@keyframes shine {
  0% {
    background-position: right;
  }
  /*100% {
    background-position: left; it's the default value, no need to define it
  }*/
}
@keyframes revealText {
  to {
    transform: translateY(-20px);
    opacity: 1;
  }
}
</style>