<template>
  <div id="main">
    <home />
  </div>
</template>

<script>
import home from '@/views/Home'

export default {
  components: {
    home
  }
};
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Press+Start+2P&display=swap");

#main {
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
</style>
