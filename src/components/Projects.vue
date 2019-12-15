<template>
    <section id="projects">
        <div class="container">
            <div class="row project-bg">
                <div class="col-12">
                    <h3>Projects of 2018 to 2020</h3>
                </div>
                <transition>
                    <button class="animatedButton" @click="letsSee">
                        Click for Additional Information
                    </button>
                </transition>
                <transition name="confirmed">
                    <div class="col-12 extra-info" v-if="show">
                        <h4>Why only 2 years? Any additional information I'd share?</h4>
                        <p>I wasn't professional until last 2 years, I used to work in a team who delivers solutions to
                            customers online, or to students by hand.Even worked on their laptop time to time. I was
                            making projects for students or I was assigned to jobs in my skillset in a non-professional
                            enviroment bringing me jobs and challanges. This experience taught me to work on other
                            developers code-base and it allows me currently to fix code rather than removing all and
                            coding from scratch, I remember a time of me fixing Medigard's, Eczacibasi : A leading
                            pharmacy company in Turkey, website 29 bugs in a friday worktime.
                        </p>
                        <p>
                            Back then I was coding Java, C# and my current tech stack, I decided to be professional
                            therefore focusing on Front-End development technologies, but as it was required I have
                            coded mobile application as well Nativescript and Flutter(which I host most of the source
                            code on my github == it is available). There is also signed NDA's in my professional working
                            enviroments as it's how it's either in my country or based on my experience. I don't have
                            few of my codebases on my Github page and most of them are Private, I also had 3 github
                            pages and I was clumsy until these last 2 years.Image used in previous section is an actual
                            screenshot from my page.</p>
                        <p>
                            I can personally explain how it was done or share my codebase privately if required, I have
                            no problem contributing to open-source projects nor helping my friends on their projects, or
                            getting into stack overflow to provide my best input to the community, but I am new to these
                            (: .
                        </p>
                    </div>
                </transition>
                    <button :class="{animatedButton : show }" v-if="show" v-on:click="showMore = !showMore">
                        Personal Information
                    </button>
                <transition name="confirmed">
                    <div id="personalsec" class="col-12 personal" v-if="showMore">
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
                    </div>
                </transition>
            </div>

            
                    <ProjectsSection/>
                
        </div>
    </section>
</template>

<script>
    import ProjectsSection from './ProjectsSection.vue';
    export default {
        data() {
            return {
                show: false,
                showMore: false,
            }
        },
        components:{
            ProjectsSection,
        },
        methods:{
            letsSee(){
                this.show = !this.show;
                this.showMore == true ? this.showMore = false : this.showMore = false;
                console.log(this.showMore);
            }
        }
    }
</script>

<style lang="scss">
    #projects {
        font-family: 'Arima Madurai', cursive;
        background-color: #00ff00;
        padding: 20px 0 60px;
        margin-top: 100px;
        *{
            transition: all .6s ease-out;
        }
        >div {
            margin-top: 50px;
            transition: all .4s;
            background-color: #111;
            box-shadow: 2px 2px 17px 10px rgba(0,0,0,0.76);
            border-radius: 15px;
            .project-bg {
                margin: 50px 0 0 0;
                color: #dedede;
                text-align: center;

                p {
                    text-align: left;
                    text-indent: 2em;
                }
            }
            button{
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
                border-radius:20px;
                border-top-width: 3px;
                box-shadow:inset 0 0 15px 20px rgb(203, 255, 182),inset 0 0 10px rgb(166, 255, 166), 0 0 15px 1px rgb(172, 255, 65),inset 0 0 20px #B6FF00, 0 0 35px #B6FF00, 0 0 40px #B6FF00, 0 0 50px #B6FF00, 0 0 75px #B6FF00;
                animation: linearGra 8s cubic-bezier(0.075, 0.82, 0.165, 1) 1s infinite normal forwards;
            }
            button:nth-of-type(2){
                margin-top: 40px;
            }
        }
    }
    @keyframes linearGra {
        0%{background-position:0% 7%;
        color: rgba(4, 32, 0, 0.815);}
        1%{
color: transparent;
        }
        2%{
color: white;
        }
        3%{
color: greenyellow;
        }
        4%{
color: transparent;
        }
        90%{
        color: #000;
        }
        100%{
        color: #fff;
        }
    }
    .confirmed-enter-active {
        height: 100%;
        transition: all 1s ease;
}
    .confirmed-leave-active {
  transition: all .7s;
}
.confirmed-enter, .confirmed-leave-to
/* .slide-fade-leave-active below version 2.1.8 */ {
  transform: translateX(100%) rotateZ(30deg);
  opacity: 0;
  float: bottom;
  height:0;
  
  max-height: 0;
  width: 0;
}

</style>