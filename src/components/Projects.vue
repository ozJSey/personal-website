<template>
  <section id="projects">
    <div class="container">
      <div class="row project-bg">
        <div class="col-12">
          <h3>Projects of 2018 to 2021</h3>
          <h4>Please keep in mind, the most accurate information would be a PDF copy of my CV which I prepare monthly!</h4>
        </div>
        <transition>
          <button
            class="animatedButton"
            @click="letsSee"
          >
            Click for Additional Information
          </button>
        </transition>
        <transition name="confirmed">
          <div
            class="col-12 extra-info"
            v-if="show"
          >
            <h1>Umm, hey... I didn't expect you'd click on this</h1>
            <p> Would you click to the next one too? 😯 </p>
            <p>Anyawys, yes! Some details about me, I prepared around 10 websites &amp; 2 libraries (1 strict JS ads plugin 1 full design system component library), some mobile applications that you perhaps wouldn't like but I love them! Please do not assume I have done only parts of them, ask me anything about'em!</p>
            <p>I also aspire to be full-stack, NodeJS and Python Flask is my preffered backend language of choice even though I've used to code in PHP.</p>
            <p>Flutter, yes please. Glad world is full of things to learn!</p>
            <p>Most of the things I know by memory in frontend, you can test it</p>
            <p>Yikes, this place sounds too egoistic, how are you? I hope you have a wonderful day because you clicked here!</p>
          </div>
        </transition>
        <button
          :class="{animatedButton : show }"
          v-if="show"
          v-on:click="showMore = !showMore"
        >
          Personal Information
        </button>
        <transition name="confirmed">
          <div
            id="personalsec"
            class="col-12 personal"
            v-if="showMore"
          >
            <h2>Time to get personal 👏</h2>
            <p>
              I laugh a lot to even to simpler things, it is a natural reaction that I never hold back,
              people around me says my laugh is funny and it also makes them laugh, without knowing what
              was my point. I like everything from light humour to dark humour but it needs to have a
              sense of intelligence in it, I don't enjoy when comedians scream to be funny. I do
              everything in my power to rescue back-end developers in non-cooperating work enviroments.
              They'd confirm that. I don't wanna sound boring here but I don't drink more than 2-3 times a
              year, I smoke tho I want to quit it. I don't play video games because I had addiction to it
              before and lessons were learned. I only play an AFK game on my mobile which requires 30 mins
              max daily. I started reading psychology and science books recently. I love cooking and I was
              a professional basketball player until the age 18. Which is sadly collage exams year in my
              country and we have a tough exam to get placed to what we want to work in, I am a graduate
              from highest score Software Engineering faculty in my country.
              Done Capstone on BEMOSS-kind as a web and mobile developer as well contributing with full
              stack website and mobile application, which is a project combining/operating all electronics
              with API's to sum up the main idea.
            </p>
            <p>
              Fun fact, I used to teach English as private and classroom tutor. I was considering this as
              a career and paused my school and was about to chase it in a collage as well. Until a
              student of mine was a software engineer and by the time I got involved in the process I
              realized how much I would love doing this compared to what I was doing back then. So I came
              back to this profession, no regrets!
            </p>
            <p>
              I also have bunch of hobbies, if you're looking for my updated CV always feel welcome to email me, ozgur.seyidoglu.sw@gmail.com.
            <ul>
              <li>I run marathons twice a year</li>
              <li>I can cook Turkish &amp; some international food!</li>
              <li>I read books like a casual</li>
              <li>I can dye hair!</li>
              <li>I know a lot about nutrition &amp; I lift daily at home!</li>
              <li>Potentially, since I won't update my website for another year, I may have actually taken playing viola seriously and may have learned by the time you read this!</li>
              <li>I enjoy inline roller-skating!</li>
              <li>Beginner level painter &amp; mid-level graffiti artist!</li>
            </ul>
            </p>
          </div>
        </transition>
      </div>

      <ProjectsSection />

    </div>
  </section>
</template>

<script>
import ProjectsSection from './ProjectsSection.vue';
export default {
  data () {
    return {
      show: false,
      showMore: false,
    }
  },
  components: {
    ProjectsSection,
  },
  methods: {
    letsSee () {
      this.show = !this.show;
      this.showMore == true ? this.showMore = false : this.showMore = false;
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
#projects {
  font-family: "Arima Madurai", cursive;
  background-color: #00ff00;
  padding: 20px 0 60px;
  margin-top: 100px;
  @include mobile {
    margin-top: 50px;
    padding: 20px 10px 60px;
  }
  * {
    transition: all 0.6s ease-out;
  }
  > div {
    margin-top: 50px;
    transition: all 0.4s;
    background-color: #121314;
    box-shadow: 2px 2px 17px 10px rgba(0, 0, 0, 0.76);
    border-radius: 15px;
    .project-bg {
      margin: 50px 0 0 0;
      color: #d8d7ed;
      text-align: center;

      p {
        text-align: left;
        text-indent: 2em;
      }
    }
    button {
      position: relative;
      background-color: #33ff00;
      background-size: 800% 800%;
      outline: 0;
      cursor: pointer;
      border: 0;
      width: 60%;
      margin-left: 20%;
      text-align: center;
      font-size: 19px;
      padding: 10px 0;
      margin-bottom: 40px;
      color: rgba(4, 32, 0, 0.815);
      border-radius: 20px;
      border-top-width: 3px;
      box-shadow: inset 0 0 15px 20px rgb(203, 255, 182),
        inset 0 0 10px rgb(166, 255, 166), 0 0 15px 1px rgb(172, 255, 65),
        inset 0 0 20px #b6ff00, 0 0 35px #b6ff00, 0 0 40px #b6ff00,
        0 0 50px #b6ff00, 0 0 75px #b6ff00;
      animation: linearGra 8s cubic-bezier(0.075, 0.82, 0.165, 1) 1s infinite
        normal forwards;

      @include mobile {
        font-size: 15px;
        width: 80%;
        margin-left: 10%;
      }
    }
    button:nth-of-type(2) {
      margin-top: 40px;
    }
  }
}
@keyframes linearGra {
  0% {
    background-position: 0% 7%;
    color: rgba(4, 32, 0, 0.815);
  }
  1% {
    color: transparent;
  }
  2% {
    color: #d8d7ed;
  }
  3% {
    color: greenyellow;
  }
  4% {
    color: transparent;
  }
  90% {
    color: #000;
  }
  100% {
    color: #fff;
  }
}
.confirmed-enter-active {
  height: 100%;
  transition: all 1s ease;
}
.confirmed-leave-active {
  transition: all 0.7s;
}
.confirmed-enter, .confirmed-leave-to
/* .slide-fade-leave-active below version 2.1.8 */ {
  transform: translateX(100%) rotateZ(30deg);
  opacity: 0;
  float: bottom;
  height: 0;

  max-height: 0;
  width: 0;
}
</style>