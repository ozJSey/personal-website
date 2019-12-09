<template>
<section id="firstSection">
  <div ref="hello" class="hello">
    <div  class="hamburger-menu">
      <button @click="show" class="hamburger-btn">
       
      </button>
       <span></span>
        <span></span>
        <span></span>
    </div>
    <div ref="banner" class="glitch-wrapper">
      <div class="glitch" data-text="OZGUR ÖS eyidoglu">OZGUR <span class="js"> JS</span>eyidoglu 
       <div class="bottom-text">
      <p class="desc">Website <span> Artistry </span></p>
      <p class="trans-desc">Welcome to my website!</p>
      </div>
    </div>
    
    </div>
    <div ref="menu" class="menu">
      <ul>
        <li><a href="#">About me</a></li>
        <li><a href="#">Skills?</a></li>
        <li><a href="#">Projects</a></li>
        <li><a href="#">CV</a></li>
        <li><a href="#">Contact</a></li>
      </ul>
    </div>
  </div>
  </section>
</template>

<script>
  export default {
    name: 'Banner',
    data(){
      return{
        active: false,
        value: 0,
      }
    },
    computed:{
    letsGo:{
       get()
        {
            return this.value
        },
        set(value)
        {
            this.value = value
        }
    }
  },
    props: {
      msg: String
    },
    methods:{
      show(e){
        console.log(e.target.children);
        let childArray = [];
        childArray.push(e.target.nextElementSibling);
        childArray.push(e.target.nextElementSibling.nextElementSibling);
        childArray.push(e.target.nextElementSibling.nextElementSibling.nextElementSibling);
        
        if(this.active == false){
          this.$refs.menu.style.top = "0";
          
          this.$refs.banner.style.transform = "perspective(200px) rotateX(10deg)";
          childArray[0].style.transform = "rotateZ(-10deg) translate3d(0, 8px, 0)";
          childArray[0].style.width = "50px";
          childArray[0].style.borderRadius = "100%";
          childArray[1].style.transform = "rotateZ(-33deg) translate3d(10px, 31px, 0px)";
          childArray[1].style.width = "25px";
          childArray[2].style.transform = "rotateZ(-163deg) translate3d(-20px, 16px, -40px)";
          childArray[2].style.width = "25px";
          this.active = true;

          setTimeout(() => {
            this.$refs.menu.style.borderTopRightRadius = "200% 10% ";
            this.$refs.menu.style.transform = "perspective(400px) rotateY(-10deg)";
          }, 300);
        }
        else{
           this.$refs.menu.style.top = "-150px";
           this.$refs.banner.style.borderTopLeftRadius = "0%";
           this.$refs.menu.style.borderTopRightRadius = "0%";
           this.$refs.menu.style.transform = "perspective(400px) rotateY(0)";
            this.$refs.banner.style.transform = "perspective(200px) rotateX(0deg)";
           childArray.forEach(el => {
             el.style.transform = "rotateZ(0) translate3d(0,0,0)";
             el.style.width = "50px";
           });
           childArray[0].style.width = "60px";
           childArray[0].style.borderRadius = "0";
           this.active = false;
        }
      }
    },
     beforeMount(){
    setInterval(() => {
      this.$refs.hello.style.filter = "hue-rotate(" + this.letsGo +'deg)';
    }, 2000);
    
  },
  mounted(){
    setInterval(() => {
      this.value += 51.42;
    }, 2000);
  }
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
  .bottom-text {
    position: absolute;
    bottom: -250px;
    display: flex;
    left: 0;
    transform: translateY(-50%);
    padding: 10px;
    color: #111;

    .trans-desc{
      position: absolute;
      top:20px;
      width: 100%;
      white-space: nowrap;
      color: white;
      font-size: 26px;
      left: 30px;
      animation: reverse-fill .7s 2s 1 ease-in forwards;
      &::first-letter {
        font-size: 35px;
        color: white;
      }
    }
    .desc {
      font-family: 'Permanent Marker', cursive;
      width: 0px;
      font-size: 26px;
      background-color: #dacb4b;
      box-shadow: 0px 0px 1px 4px rgba(233, 213, 77, .2);
      animation: fill 1s 3s 1 ease-in forwards;
      padding: 10px 20px;
      border-radius: 7px;

      &::first-letter {
        font-size: 35px;
        color: white;
      }

      span {
        margin-left: 30px;
        display: block;
      }
    }

  }
  .menu{
    position : absolute;
    right: 0;
    transition: all ease-in-out .8s;
    background-color: #e9d54d;
    z-index: -1;
    color: white;
    top: -190px;
    width: 50%;
    box-shadow: 0 0 2px 0px rgba(158, 143, 41, .1);
    ul{
      width: 100%;
      list-style: none !important;
      padding-left:20px;
      display: flex;
      li{
        margin: 10px 20px;
        font-size: 24px;
        position: relative;
        a{
          position: relative;
          letter-spacing: .03rem;
          color: #222;
          text-decoration: none;
       
        &:after{
          content: '';
          position: absolute;
          width: 0;
          left: 0;
          height:3px;
          bottom: -3px;
          transition: width .4s ease-out;
          background-color: #222;
        }
        &:hover{
           &:after{
            animation: boing .4s ease-in .2s 1 forwards;
           }
        } 
        }
      }
    }
  }

  @keyframes fill {
    to {
      color: white;
      width: 100%;
    }
  }
  @keyframes reverse-fill{
    to{
      color: transparent;
      width: 0;
    }
  }
  @keyframes boing {
    50%{
      width: 120%;
    }
     60%{
      width: 120%;
    }
     70%{
      width: 100%;
    }
     80%{
      width: 110%;
    }
     90%{
      width: 90%;
    }
    100%{
      width: 100%;
    }
  }
  .hamburger-menu {
    position: absolute;
    top: 100px;
    left: 50px;
    display: flex;
    z-index: 3;

    .hamburger-btn {
      outline: none;
      border: none;
      padding: 30px;
      cursor: pointer;
      background-color: transparent;
      display: flex;
      flex-direction: column;
      z-index: 5;
      
    }
    span {
        position: absolute;
        background-color: rgb(233, 213, 77);
        width: 50px;
        box-shadow: 0px 0px 2px 2px rgba(233, 213, 77, .2);
        height: 6px;
        margin: 3px;
        top: 10px;
        transition: all .3s ease-in;

        &:first-child{
          width: 60px;
          top: 10px;
        }
        &:nth-child(2){
          width: 60px;
          top: 20px;
        }
        &:last-child{
          width: 50px;
          top:30px;
        }
      }
  }

  .js {
    background-color: rgb(233, 213, 77);
    padding: 0 15px;
    color: #222;
    font-weight: 600;
    border-radius: 5px;
    font-size: 90px;
    box-shadow: 0px 0px 1px 4px rgba(233, 213, 77, .2);
  }

  .hello {
    height: 100vh;
    position: relative;
    width: 100vw;font-family: 'Permanent Marker', cursive;
  }

  .glitch-wrapper {
    height: 100%;
    display: flex;
    transition: all .7s ease-out;
     background: #111;
    justify-content: center;
    z-index: 1;
    align-items: center;
    box-shadow: 2px -7px 17px 10px rgba(0,0,0,0.96);
  }

  .glitch {
    color: white;
    font-size: 90px;
    text-transform: upercase;
    position: relative;
    display: inline-block;
  }

  .glitch::before,
  .glitch::after {
    content: attr(data-text);
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background: #111;
  }

  .glitch::before {
    left: 2px;
    text-shadow: -2px 0 rgb(0, 233, 250);
    clip: rect(24px, 550px, 90px, 0);
    animation: glitch-anim-2 3s infinite linear alternate-reverse;
  }

  .glitch::after {
    left: -2px;
    text-shadow: -2px 0 #ebfc00;
    clip: rect(85px, 550px, 160px, 0);
    animation: glitch-anim 2.5s infinite linear alternate-reverse;
  }

  @keyframes glitch-anim {
    0% {
      clip: rect(0px, 9999px, 86px, 0);
    }

    4.166666666666666% {
      clip: rect(53px, 9999px, 121px, 0);
    }

    12.5% {
      clip: rect(20px, 9999px, 11px, 0);
    }

    16.666666666666664% {
      clip: rect(77px, 9999px, 80px, 0);
    }

    20.833333333333336% {
      clip: rect(45px, 9999px, 26px, 0);
    }

    25% {
      clip: rect(7px, 9999px, 9px, 0);
    }

    29.166666666666668% {
      clip: rect(39px, 9999px, 23px, 0);
    }

    33.33333333333333% {
      clip: rect(23px, 9999px, 52px, 0);
    }

    37.5% {
      clip: rect(5px, 9999px, 42px, 0);
    }

    50% {
      clip: rect(110px, 9999px, 29px, 0);
    }

    54.166666666666664% {
      clip: rect(6px, 9999px, 53px, 0);
    }

    58.333333333333336% {
      clip: rect(78px, 9999px, 82px, 0);
    }

    62.5% {
      clip: rect(20px, 9999px, 89px, 0);
    }

    66.66666666666666% {
      clip: rect(32px, 9999px, 20px, 0);
    }

    70.83333333333334% {
      clip: rect(130px, 9999px, 97px, 0);
    }

    75% {
      clip: rect(107px, 9999px, 26px, 0);
    }

    100% {
      clip: rect(97px, 9999px, 46px, 0);
    }
  }

  @-webkit-keyframes glitch-anim-2 {
    6.666666666666667% {
      clip: rect(43px, 9999px, 83px, 0);
    }

    10% {
      clip: rect(148px, 9999px, 27px, 0);
    }

    13.333333333333334% {
      clip: rect(27px, 9999px, 124px, 0);
    }

    16.666666666666664% {
      clip: rect(82px, 9999px, 128px, 0);
    }

    20% {
      clip: rect(124px, 9999px, 88px, 0);
    }

    23.333333333333332% {
      clip: rect(19px, 9999px, 68px, 0);
    }

    26.666666666666668% {
      clip: rect(60px, 9999px, 71px, 0);
    }

    30% {
      clip: rect(61px, 9999px, 3px, 0);
    }

    33.33333333333333% {
      clip: rect(48px, 9999px, 76px, 0);
    }

    36.666666666666664% {
      clip: rect(71px, 9999px, 1px, 0);
    }

    40% {
      clip: rect(78px, 9999px, 6px, 0);
    }

    43.333333333333336% {
      clip: rect(82px, 9999px, 129px, 0);
    }

    46.666666666666664% {
      clip: rect(87px, 9999px, 106px, 0);
    }

    50% {
      clip: rect(73px, 9999px, 31px, 0);
    }

    53.333333333333336% {
      clip: rect(160px, 9999px, 105px, 0);
    }

    56.666666666666664% {
      clip: rect(35px, 9999px, 39px, 0);
    }

    60% {
      clip: rect(63px, 9999px, 133px, 0);
    }

    63.33333333333333% {
      clip: rect(13px, 9999px, 22px, 0);
    }

    66.66666666666666% {
      clip: rect(68px, 9999px, 94px, 0);
    }

    70% {
      clip: rect(35px, 9999px, 67px, 0);
    }

    73.33333333333333% {
      clip: rect(12px, 9999px, 65px, 0);
    }

    76.66666666666667% {
      clip: rect(122px, 9999px, 38px, 0);
    }

    80% {
      clip: rect(30px, 9999px, 24px, 0);
    }

    83.33333333333334% {
      clip: rect(22px, 9999px, 105px, 0);
    }

    86.66666666666667% {
      clip: rect(135px, 9999px, 73px, 0);
    }

    90% {
      clip: rect(44px, 9999px, 18px, 0);
    }

    93.33333333333333% {
      clip: rect(91px, 9999px, 15px, 0);
    }

    96.66666666666667% {
      clip: rect(104px, 9999px, 43px, 0);
    }

    100% {
      clip: rect(122px, 9999px, 39px, 0);
    }
  }

  @keyframes glitch-anim-2 {
    6.666666666666667% {
      clip: rect(43px, 9999px, 83px, 0);
    }

    10% {
      clip: rect(148px, 9999px, 27px, 0);
    }

    13.333333333333334% {
      clip: rect(27px, 9999px, 124px, 0);
    }

    16.666666666666664% {
      clip: rect(82px, 9999px, 128px, 0);
    }

    20% {
      clip: rect(124px, 9999px, 88px, 0);
    }

    23.333333333333332% {
      clip: rect(19px, 9999px, 68px, 0);
    }

    26.666666666666668% {
      clip: rect(60px, 9999px, 71px, 0);
    }

    30% {
      clip: rect(61px, 9999px, 3px, 0);
    }

    33.33333333333333% {
      clip: rect(48px, 9999px, 76px, 0);
    }

    36.666666666666664% {
      clip: rect(71px, 9999px, 1px, 0);
    }

    40% {
      clip: rect(78px, 9999px, 6px, 0);
    }

    43.333333333333336% {
      clip: rect(82px, 9999px, 129px, 0);
    }

    46.666666666666664% {
      clip: rect(87px, 9999px, 106px, 0);
    }

    50% {
      clip: rect(73px, 9999px, 31px, 0);
    }

    53.333333333333336% {
      clip: rect(160px, 9999px, 105px, 0);
    }

    56.666666666666664% {
      clip: rect(35px, 9999px, 39px, 0);
    }

    60% {
      clip: rect(63px, 9999px, 133px, 0);
    }

    63.33333333333333% {
      clip: rect(13px, 9999px, 22px, 0);
    }

    66.66666666666666% {
      clip: rect(68px, 9999px, 94px, 0);
    }

    70% {
      clip: rect(35px, 9999px, 67px, 0);
    }

    73.33333333333333% {
      clip: rect(12px, 9999px, 65px, 0);
    }

    76.66666666666667% {
      clip: rect(122px, 9999px, 38px, 0);
    }

    80% {
      clip: rect(30px, 9999px, 24px, 0);
    }

    83.33333333333334% {
      clip: rect(22px, 9999px, 105px, 0);
    }

    86.66666666666667% {
      clip: rect(135px, 9999px, 73px, 0);
    }

    90% {
      clip: rect(44px, 9999px, 18px, 0);
    }

    93.33333333333333% {
      clip: rect(91px, 9999px, 15px, 0);
    }

    96.66666666666667% {
      clip: rect(104px, 9999px, 43px, 0);
    }

    100% {
      clip: rect(122px, 9999px, 39px, 0);
    }
  }
</style>