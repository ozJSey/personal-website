<template>
    <section id="contactMe">
        <div class="container">
            <div class="row">
                <div class="col-12 contactContent">
                    <button ref="one" @click="sendForm" class="animateButton">Say Hi!</button>
                </div>
                <div @click="reverseSendForm" class="col-12 contactForm">
                    <h2> Özgür Seyidoglu </h2>
                    <input type="text" id="email" @click="copy" value="ozgur.seyidoglu.sw@gmail.com">
                    <a target="_blank" href="https://www.linkedin.com/in/ozgur-seyidoglu-024449168/"> <font-awesome-icon class="animateIcon" :icon="[ 'fab', 'linkedin' ]"> </font-awesome-icon></a>
                    <p style="text-align:center">Thank you for visiting my website!</p>
                </div>
                 <div id="subText">
                        Copied!
                    </div>
            </div>
        </div>
    </section>
</template>

<script>
export default {
    methods: {
        sendForm(e){
            let father = document.querySelector('.contactContent');
            let infoCard = document.querySelector('.contactForm');
            father.style.transform = "translateY(200%)";
            e.target.style.animation = "none";
            infoCard.style.bottom = "-20%";
            let infoArray = infoCard.children;
            infoArray = [...infoArray];
            infoArray.forEach(element => {
                setTimeout(() => {
                    element.style.transition = "all 5s";
                    element.classList = 'animate';
                }, 1200);
            });
        },
        reverseSendForm(e){
            let father = document.querySelector('.contactContent');
            let infoCard = document.querySelector('.contactForm');
            father.style.transform = "translateY(0)";
            this.$refs.one.style.animation = "float 6s ease-in-out alternate infinite";
            infoCard.style.bottom = "50%";
            let infoArray = infoCard.children;
            infoArray = [...infoArray];
            infoArray.forEach(element => {
                     element.classList = ' ';
            });
        },
        copy(){
            var copyText = document.getElementById("email");
            copyText.select();
            copyText.setSelectionRange(0, 99999);
            document.execCommand("copy");
            document.getElementById('subText').classList="small-show";
            setTimeout(() => {
                document.getElementById('subText').classList=""; 
            }, 2000);
        }
    },
}
</script>

<style lang="scss">
@mixin mobile{
    @media (max-width: 992px){
        @content;
    }
}
    #contactMe{
        margin-top: 100px;
        position: relative;
        overflow: hidden;
        font-family: 'Permanent Marker', cursive;
        height: 50vh;
        display: flex;
        justify-self: center;
        align-items: center;
        width: 100vw;
        background-color: #ff00ff;
        display: flex;
        justify-content: center;
        align-items: center;
        @include mobile{
            margin-top: 50px;
        }
        .contactContent{
            text-align: center;
            transition: transform 1s ease-out;
            button.animateButton{
                width: 30vh;
                font-family: 'Permanent Marker', cursive;
                font-size: 25px;
                height: 30vh;
                cursor: pointer;
                transition: transform 1s;
                outline: 0;
                background: linear-gradient(120deg, rgb(43, 255, 0) 6%, rgb(255, 251, 1) 54%, rgba(255,0,209,1) 100%);
                border-radius: 15vh;
                user-select: none;
                border-width: 0;
                animation: float 6s ease-in-out alternate infinite;
                background-size: 300% 300%;
                &::after{
                    content: 'Say Hi!';
                    position: absolute;
                    top: 50%;
                    display: flex;
                    align-items: center;
                    justify-content: center;
                    color: #060607;
                    left: 50%;
                    transform: translate(-50%, -50%);
                    width: 25vh;
                    height: 25vh;
                    border-radius: 25vh;
                    background-color: #d8d7ed;
                }
            }
        }
        .contactForm{
            position: absolute;
            text-align: center;
            transition: all 1s;
            left: 0;
            display: flex;
            justify-content: center;
            align-items: center;
            flex-direction: column;
            justify-self: center;
            transform: translateY(-50%);
            bottom: 400px;
            padding: 15px;
            cursor: pointer;
            p{
                color: transparent;
                transition: all 1s ease;
                &.animate{
                    animation: text .5s cubic-bezier(0.075, 0.82, 0.165, 1) 0s 1 normal forwards;
                }
            }
            h2{
                color: transparent;
                transition: all 1s ease;
                &.animate{
                    animation: text .5s cubic-bezier(0.075, 0.82, 0.165, 1) 1.5s 1 normal forwards;
                }
            }
            a{
                transform: translateY(-50px);
                z-index: 5;
                transition: all 1s ease;
                svg{
                    color: transparent;
                    font-size: 35px;transition: all 1s ease-in;     
                }
                &.animate{
                    animation: text .5s cubic-bezier(0.075, 0.82, 0.165, 1) 2s 1 normal forwards;

                    svg{
                    color: #fdecff;
                    font-size: 35px;        
                    }
                }
            }
            input{
                font-family: 'Arima Madurai', cursive;
                background-color: transparent;
                transition: all 1s ease;
                width: 100%;
                cursor: pointer;
                margin-bottom: 10px;
                text-align: center; 
                padding: 10px;
                font-size: 21px;
                outline: 0;
                border:0;
                color: transparent;

                &.animate{
                    animation: text .5s cubic-bezier(0.075, 0.82, 0.165, 1) 2.5s 1 normal forwards;
                }
            }
        }
        #subText{
            position: absolute;
            bottom: 10%;
            opacity: 0;
            left: 50%;
            z-index: 0;
            transform: translateX(-50%);
            background-color: rgba(0,0,0,0.85);
            color: #d8d7ed;
            padding: 10px 30px;
            border-radius: 50px;
            transition: all .5s ease-in;
            &.small-show{
                animation: show 2s ease-in .3s 1 normal;
            }
        }
    }
    @keyframes float {
	0% {
		box-shadow: 0 5px 24px 5px rgba(0,0,0,0.6);
		transform: translateY(0px);
        background-position: 200% 100%;
	}
	50% {
		box-shadow: 0 35px 20px 10px rgba(0,0,0,0.2);
		transform: translateY(-30px);
        background-position: 10% 270%;
	}
	90% {
		box-shadow: 0 5px 6px 0px rgba(0,0,0,0.8);
		transform: translateY(5px);
        background-position: 275% 40%;
	}
}
@keyframes text {
    95%{
        color: #d8d7ed;
    } 
    100%{
        transform: translateY(30px);
        color: #fdecff;
    }       
}
@keyframes show {
    90%{
        opacity: 1;
    }
}
</style>