<template>
  <div style="text-align: center; margin-top: 30vw;">
    <h1 style="font-family: Roboto; color: white;"><b>{{score}}</b></h1>  
<div style="text-align: center; display: flex; align-items: center; justify-content: center;">
    <a class="click" @click="click()"><img src="https://i.postimg.cc/Bbx7rKd1/IMG-2281.png" width="500px"></a> 
</div>
<div style="text-align: center; display: flex; align-items: center; justify-content: center; color: white; font-family: Roboto; margin-top: -20vw;">
  <p>3000/3000</p>
  <img src="https://em-content.zobj.net/source/telegram/386/high-voltage_26a1.webp" style="width: 5vw; margin-left: 2px;">
</div>  
</div>
  <div class="box">
    <button class="up">Upgrade</button>
    <button class="game"><b>Games</b></button>
    <RouterLink to="/about"><button class="ref">Ref</button></RouterLink>
  </div>
</template>
  
<style scoped>
  .box {
    background-color: black;
    width: 105vw;
    position: absolute;
    height: 80px;
    bottom: 0;
    margin-left: -2vw;
    margin-top: auto;
  }
  .up {
    background-color: black;
    color: white;
    border: none;
    width: 33%;
    height: 80px;
  }
  .game {
    background-color: black;
    color: white;
    border: none;
    width: 33%;
    height: 80px;
  }
  .ref {
    background-color: black;
    color: white;
    border: none;
    width: 34%;
    height: 80px;
  }
</style>
  
<script>
  import { ref } from 'vue';
      
      export default {
      
        setup() {
          const score = ref(localStorage.getItem('score') ? parseInt(localStorage.getItem('score')) : 0);
      
          const click = () => {
            score.value += 1;
            saveScore();
          };
      
          const saveScore = () => {
            localStorage.setItem('score', score.value);
          };
      
          return {
            score,
            click,
          };
        },
      };
</script>
