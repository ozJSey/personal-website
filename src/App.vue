<template>
  <div id="app">
    <Banner/>
    <AboutMe/>
    <Fun/>
  </div>
</template>

<script>
import Banner from './components/Banner.vue';
import AboutMe from './components/AboutMe.vue';
import Fun from './components/Fun.vue';

export default {
  name: 'app',
  components: {
    Banner,
    AboutMe,
    Fun
  },
 
}
</script>

<style lang="scss">
#app{
  overflow: hidden;
}
  body{
    background: linear-gradient(to right, 
      #FFFFFF    14%, 
      #FFFF00  14%, 
      #FFFF00  28%, 
      #00FFFF  28%, 
       #00FFFF  42%, 
      #00FF00 42%, 
      #00FF00 56%, 
      #FF00FF 56%,
      #FF00FF 70%,
      #FF0000 70%,
      #FF0000 84%,
      #0000FF 84%,
      #0000FF 96%,
      #0000FF 96%,
  );
    background-size: 40%;
    background-position: 7%;
    background-repeat: no-repeat;
    margin: 0;
    padding:0;
  }
</style>
