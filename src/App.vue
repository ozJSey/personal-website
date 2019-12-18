<template>
  <div id="app">
    <Banner/>
    <AboutMe/>
    <Fun/>
    <Projects/>
    <ContactMe/>
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
window.addEventListener('onmousemove', (e) =>{
      console.log(e);
    });
</script>

<style lang="scss">
@mixin mobile{
  @media (max-width: 992px) { @content; }
} 
#app{
  overflow: hidden;
  ::selection {
    background: rgba(233, 213, 77, 0.8);
 }

}
::-webkit-scrollbar-track{
	box-shadow: inset 0 0 6px rgba(0,0,0,0.3);
	border-radius: 50px;
	background-color: #121314;
}

::-webkit-scrollbar{
	width: 12px;
	background-color: #121314;
}

::-webkit-scrollbar-thumb{
    height: 20%;
	  background: linear-gradient(140deg, rgba(233, 213, 77, 1) 95%, #121314 95%);
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
    @include mobile{
      background: linear-gradient(to right, 
      #FFFFFF  5%, 
      #FFFF00  5%, 
      #FFFF00  22%, 
      #00FFFF  22%, 
       #00FFFF 39%, 
      #00FF00 39%, 
      #00FF00 56%, 
      #FF00FF 56%,
      #FF00FF 73%,
      #FF0000 73%,
      #FF0000 90%,
      #0000FF 90%,
      #0000FF 100%,
      #0000FF 100%,
  );
    }
  }
</style>
