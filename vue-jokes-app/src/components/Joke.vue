<template>
<div class="main">
    <div class="flex-container">
    <div id="title-div">
        <h1 id="title">Teacher Jokes</h1>
        <p id="directions">Out of this world funny</p>
    </div>
    <div id="jokes-container" class="container">
        <h2 id="jokes-text" class="text-center">{{ joke.joke }}</h2>
    </div>
    <button id="jokes-button" class="btn btn-primary" @click="getJoke">click for joke</button>
    </div>
    <div id="credits" class="text-center">
        <p>Jokes credit to: www.icanhazdadjoke.com. Website dedicated to teachers who need some new material</p>
    </div>
</div>

</template>

<script>
import jokeService from "@/services/JokeService";
export default {
    name: "joke",
    data() {
        return {
            joke: {
                "id": 0,
                "joke": "",
                "status": 0
            }

        }
        },
        methods: {
            getJoke() {
                jokeService.getJoke().then((response) => {
                    if (response.status == 200 || response.status == 201){
                        this.joke = response.data;
                        console.log('all good');
                    }
                })
                .catch(err => console.log('ERROR: ' + err));
            }
        }

    }
</script>

<style scoped>
@import url("https://fonts.googleapis.com/css2?family=Press+Start+2P&display=swap");

.main {
    font-family:"Press Start 2P", cursive;
    background-image:url(https://www.pcclean.io/wp-content/uploads/2020/4/I7FjYn.jpg);
    background-size:cover;
    color:#FFF;
    text-align:center;
    width:100vw;
    height:100vh;
    margin: 0 auto;
    display: flex;
    }


#jokes-text {
        font-size: 20px;
    }

    #title-div {
    display:flex;
    flex-direction:column;
    text-align:center;
    align-items:center;
    gap:20px;
    margin-top:20px;
    margin-bottom:20px;
    margin-left: auto;
    margin-right: auto;
    width: 100vw;
    }
    
    #title {
    display: flex;
    text-shadow:1px 1px 1px #919191, 1px 2px 1px #919191, 1px 3px 1px #919191, 1px 4px 1px #919191, 1px 5px 1px #919191, 1px 6px 1px #919191, 1px 7px 1px #919191, 1px 8px 1px #919191, 1px 9px 1px #919191, 1px 10px 1px #919191, 1px 18px 6px rgba(16,16,16,0.4), 1px 22px 10px rgba(16,16,16,0.2), 1px 25px 35px rgba(16,16,16,0.2), 1px 30px 60px rgba(16,16,16,0.4);
    }
    
    #jokes-container {
    height:20vh;
    width:80vw;
    flex-direction:column;
    margin-top: 10vh;
    margin-left: auto;
    margin-right: auto;
    }
    
    .btn {
    width:fit-content;
    justify-content:center;
    font-size:1vw;
    cursor:pointer;
    transition:all .3s ease;
    border-radius:50px;
    box-shadow: var(--primary-color), .5 0 0 20px 0;
    margin-right: auto;
    margin-left: auto;
    margin-top: 10vh;
    margin-bottom: 0;
    padding:12px 32px;
    } 

    #credits {
    position: absolute;
    bottom: 0;
    right: 0;
    left: 0;
    width:100%;
    height: 3em;
    font-family:sans-serif;
    text-align: center;
    }

</style>