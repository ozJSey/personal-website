<template>
    <section id="contactMe">
        <div class="container">
            <div class="row">
                <div class="col-12 contactContent">
                    <button>Say Hi!</button>
                </div>
            </div>
        </div>
    </section>
</template>

<script>
export default {

}
</script>

<style lang="scss">
    #contactMe{
        margin-top: 100px;
        font-family: 'Permanent Marker', cursive;
        height: 50vh;
        width: 100vw;
        background-color: #ff00ff;
        display: flex;
        justify-content: center;
        align-items: center;
        .contactContent{
            text-align: center;
            button{
                width: 30vh;
                font-family: 'Permanent Marker', cursive;
                font-size: 25px;
                height: 30vh;
                transition: all .2s;
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
                    color: #222;
                    left: 50%;
                    transform: translate(-50%, -50%);
                    width: 25vh;
                    height: 25vh;
                    border-radius: 25vh;
                    background-color: white;
                }
            }
        }
        
    }
    @keyframes float {
	0% {
		box-shadow: 0 5px 24px 5px rgba(0,0,0,0.6);
		transform: translatey(0px);
        background-position: 200% 100%;
	}
	50% {
		box-shadow: 0 35px 20px 10px rgba(0,0,0,0.2);
		transform: translatey(-30px);
        background-position: 10% 270%;
	}
	90% {
		box-shadow: 0 5px 6px 0px rgba(0,0,0,0.8);
		transform: translateY(5px);
        background-position: 275% 40%;
	}
}
</style>