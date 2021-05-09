<template>
  <div id="app">
    <Banner />
    <AboutMe />
    <Fun />
    <Projects />
    <ContactMe />
  </div>
</template>

<script>
import Banner from './components/Banner.vue';
import AboutMe from './components/AboutMe.vue';
import Fun from './components/Fun.vue';
import Projects from './components/Projects.vue';
import ContactMe from './components/ContactMe.vue';
export default {
  name: 'app',
  components: {
    Banner,
    AboutMe,
    Fun,
    Projects,
    ContactMe
  },
}
const
  scrollTo = function (to, duration) {
    const
      element = document.scrollingElement || document.documentElement,
      start = element.scrollTop,
      change = to - start,
      startDate = +new Date(),
      // t = current time
      // b = start value
      // c = change in value
      // d = duration
      easeInOutQuad = function (t, b, c, d) {
        t /= d / 2;
        if (t < 1) return c / 2 * t * t + b;
        t--;
        return -c / 2 * (t * (t - 2) - 1) + b;
      },
      animateScroll = function () {
        const currentDate = +new Date();
        const currentTime = currentDate - startDate;
        element.scrollTop = parseInt(easeInOutQuad(currentTime, start, change, duration));
        if (currentTime < duration) {
          requestAnimationFrame(animateScroll);
        }
        else {
          element.scrollTop = to;
        }
      };
    animateScroll();
  };
</script>

<style lang="scss">
@mixin mobile {
  @media (max-width: 992px) {
    @content;
  }
}
#app {
  overflow: hidden;
  ::selection {
    background: rgba(233, 213, 77, 0.8);
  }
}
::-webkit-scrollbar-track {
  box-shadow: inset 0 0 6px rgba(0, 0, 0, 0.3);
  border-radius: 50px;
  background-color: #121314;
}

::-webkit-scrollbar {
  width: 12px;
  background-color: #121314;
}

::-webkit-scrollbar-thumb {
  height: 20%;
  background: linear-gradient(140deg, rgba(233, 213, 77, 1) 95%, #121314 95%);
}
body {
  background: linear-gradient(
    to right,
    #ffffff 14%,
    #ffff00 14%,
    #ffff00 28%,
    #00ffff 28%,
    #00ffff 42%,
    #00ff00 42%,
    #00ff00 56%,
    #ff00ff 56%,
    #ff00ff 70%,
    #ff0000 70%,
    #ff0000 84%,
    #0000ff 84%,
    #0000ff 96%,
    #0000ff 96%
  );
  scroll-behavior: smooth;
  background-size: 40%;
  background-position: 7%;
  background-repeat: no-repeat;
  margin: 0;
  padding: 0;
  @include mobile {
    background: linear-gradient(
      to right,
      #ffffff 5%,
      #ffff00 5%,
      #ffff00 22%,
      #00ffff 22%,
      #00ffff 39%,
      #00ff00 39%,
      #00ff00 56%,
      #ff00ff 56%,
      #ff00ff 73%,
      #ff0000 73%,
      #ff0000 90%,
      #0000ff 90%,
      #0000ff 100%,
      #0000ff 100%
    );
  }
}
</style>
