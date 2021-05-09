<template>
  <section id="rate">
    <div class="container">
      <div class="playground">
        <img
          src="../assets/Github.png"
          alt=""
          class="img-fluid"
          srcset=""
        >

        <span></span>
        <span></span>
        <span></span>
        <span></span>
        <span></span>
        <p>It's funny</p>
        <p>To see</p>
        <p>People Rate</p>
        <p>Themselves...</p>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  methods: {
    handleScroll (e) {
      let a = document.querySelector('.playground');
      let childs = a.children;
      childs = [...childs];
      if (window.scrollY > (a.scrollTop + a.offsetHeight / 2) && (window.scrollY > (a.scrollTop + a.offsetHeight * 2))) {
        childs.forEach(element => {
          element.classList = "animate";
        });
      }
      else {
        childs.forEach(element => {
          element.classList = "";
        });
      }

    }
  },
  created () {
    window.addEventListener('scroll', this.handleScroll);
  },
  destroyed () {
    window.removeEventListener('scroll', this.handleScroll);
  }
}
</script>

<style lang="scss">
@mixin mobile {
  @media (max-width: 992px) {
    @content;
  }
}
#rate {
  margin-top: 100px;
  position: relative;
  background-color: #00ffff;
  @include mobile {
    margin-top: 50px;
  }
  > div {
    img {
      max-width: 100%;
      transition: all 1s ease-in;
      height: auto;
      border: 1px solid transparent;
      border-radius: 15px;
      &.animate {
        box-shadow: 2px -2px 27px -2px rgba(0, 0, 0, 0.89);
        transform: perspective(100px) rotateZ(3deg) skewX(5deg)
          translate(-10px, 30px);
      }
    }
    &::after {
      content: "";
      position: absolute;
      top: 50%;
      right: 0;
      transform: translateY(-50%);
      height: 5px;
      background-color: #00ffff;
      width: 50%;
      box-shadow: 5px 2px 3px 5px #0ffff0, 11px 0px 3px 2px rgb(12, 179, 179);
      z-index: 1;
    }

    &::before {
      content: "";
      position: absolute;
      top: 40%;
      right: 0;
      transform: translateY(-50%);
      height: 5px;
      background-color: #00ffff;
      box-shadow: 5px 2px 3px 5px #00fff0, 11px 0px 3px 2px rgb(12, 179, 179);
      width: 40%;
      z-index: 1;
    }
    margin-top: 50px;
    .playground {
      position: relative;
      margin: 50px 0;

      span {
        position: absolute;
        background-color: #00ffff;
        height: 100%;
        font-size: 36px;
        left: 0;
        z-index: 1;
        border-radius: 0;

        &.animate:nth-of-type(1) {
          top: 25%;
          height: 50px;
          animation: jiggle 1.5s normal 1.3s 1 linear forwards;
        }
        &.animate:nth-of-type(2) {
          top: 32%;
          height: 50px;
          animation: jiggle 1.5s normal 2.3s 1 linear forwards;
        }
        &.animate:nth-of-type(3) {
          top: 39%;
          height: 50px;
          animation: jiggle 1.5s normal 2.8s 1 linear forwards;
        }
        &.animate:nth-of-type(4) {
          top: 46%;
          height: 50px;
          animation: jiggle 1.5s normal 3.4s 1 linear forwards;
        }
        &.animate:nth-of-type(5) {
          top: 53%;
          height: 50px;
          animation: jiggle 1.5s normal 4s 1 linear forwards;
        }
      }
      p {
        font-family: "Arima Madurai", cursive;
        position: absolute;
        background-color: #00ffff;
        height: 100%;
        font-weight: 600;
        padding-left: 20px;
        color: transparent;
        font-size: 36px;
        right: 0;
        z-index: 1;
        border-radius: 0;

        @include mobile {
          font-size: 25px;
        }
        &.animate:nth-of-type(1) {
          top: 22%;
          height: 50px;
          animation: jiggle 1.5s reverse 1s 1 linear forwards;
        }
        &.animate:nth-of-type(2) {
          top: 30%;
          height: 50px;
          animation: jiggle 1.5s reverse 2s 1 linear forwards;
        }
        &.animate:nth-of-type(3) {
          top: 38%;
          height: 50px;
          animation: jiggle 1.5s reverse 3s 1 linear forwards;
        }
        &.animate:nth-of-type(4) {
          top: 46%;
          height: 50px;
          animation: jiggle 1.5s reverse 4s 1 linear forwards;
        }
      }
      * {
        border-radius: 15px;
      }

      padding: 50px 0;
      &::after {
        content: "";
        position: absolute;
        box-shadow: 1px 0px 3px 2px rgb(12, 179, 179);
        top: 0;
        border-radius: 15px;
        left: 0;
        width: 100%;
        height: calc(100% - 100px);
        margin-top: 50px;
        background: linear-gradient(
          110deg,
          transparent -20%,
          white 25% 70%,
          rgba(0, 0, 0, 0.99) 70%
        );
        background-position: 60%;
      }
    }
  }
}
@keyframes jiggle {
  0% {
    width: 100%;
    background-color: transparent;
    opacity: 1;
    color: #222;
  }
  50% {
    width: 90%;
    transform: translate(-5px, -5px);
  }
  60% {
    width: 90%;
    text-shadow: 1px 1px 2px #121314;
  }
  80% {
    opacity: 1;
    color: #00ffff;
  }
  100% {
    width: 0;
    opacity: 0;
  }
}
</style>