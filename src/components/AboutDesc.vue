<template>
  <section ref="sideSection" @click="enlarge" class="some-text animated">
      <h1>Özgür Seyidoğlu</h1>
      <p>Hello, I am a Front-End developer from Turkey. I also develop mobile apps for fun/professional reasons.</p>
      <p>I have been into development from freelance to professional and now international enviroments</p>
      <p>I code pretty much day and night! </p>
      <p>My preffered way to call myself is "Production-ready front-end developer who does mobile sometimes"</p>
      <p>With all these being said, I want to finish with a side note. I have no idea if I can share my code.I don't want to be sued :( Can totally share privately if asked.</p>
      <div :class="{opacity: extended}" class="side-title">
         <p> More information!</p>
      </div>
  </section>
</template>

<script>
export default {
    data(){
            return{
                extended: false
            }
        },
    methods:{    
        enlarge(){
            if(this.extended == false){
            this.$refs.sideSection.style.right = 0;
            this.$refs.sideSection.classList = 'some-text';
            this.extended = true;
                let fatherDiv = document.querySelector('.some-text');
                fatherDiv.children.forEach((el)=>{
                    el.classList = "reveal";
                });
            }
            else{
                this.$refs.sideSection.style.right = "95vw";
                this.$refs.sideSection.classList = 'some-text animated';
                this.extended = false;
                let fatherDiv = document.querySelector('.some-text');
                fatherDiv.children.forEach((el)=>{
                    el.classList = "";
                });
            }
        }
    }
}
</script>

<style lang="scss">
    .some-text{
        position: absolute;
        top: 50px;
        width: 100vw;
        border-radius: 0;
        transition: right .4s ease-in;
        right: 95vw;
        cursor: pointer;
        background-color: #111;
        background-image: linear-gradient(
        to right,
        transparent 33%,
        rgba(255,255,255,0.3) 50%,
        transparent 66%
  );
  background-size:300% 100%;
  animation: shine 1s 2;
        box-shadow: 2px 2px 17px 10px rgba(0, 0, 0, 0.96);
        &.animated{
            animation: shakeItUpBebegim 4s normal 0s infinite ease-in;
            border-radius: 15px;
        }
        
        color: #f0f0f0;
        h1,p{
            text-align: center;
        }
        p{  
            opacity: 0;
            padding:0 70px;
        }
        h1{
            opacity: 0;
            margin-top: 40px;
        }
        h1.reveal{
            animation: revealText .6s  .12s 1 ease-in forwards;
        }
        p.reveal{
            animation: revealText .6s  1.15s 1 ease-in forwards;
        }
        .side-title{
            position: absolute;
            right: -145px;
            top: 117px;
            cursor: pointer;
            transition: opacity .4s ease-out;
            opacity: 1;
            &.opacity{
                opacity: 0;
            }
            p{  
                transform: rotate(90deg);
                font-size: 26px;
                opacity: 1;
            }
        }
    }
    @keyframes shakeItUpBebegim {
        0%{
            transform: translateX(0px);
        }
        25%{
            transform: translateX(-2px);
        }
        50%{
            transform : translateX(5px);
        }
        80%{
            transform: translateX(-5px);
        }
        100%{
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
    to{
        transform: translateY(-20px);
        opacity: 1;
    }
}
</style>