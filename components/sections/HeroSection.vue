<template>
  <div class="container">
    <div style="position: relative;" class="wrapper">
      <div class="texts">
        <h1>Siti web professionali per tutti</h1>
        <p>Design moderno, funzionalità avanzate e prezzi che si adattano a te. Perché un buon sito non deve essere un lusso.</p>
        <div class="btns">
          <button>Richiedi un preventivo</button>
          <button v-show="width > 768">Contattami</button>
        </div>
      </div>

      <div class="imgContainer">
        <img class="floating-img" src="../../assets/img/pc.svg" alt="">
      </div>
    </div>
  </div>
  <div style="background-color: transparent; margin: 0; display: block; padding: 0;" class="waveContainer">
    <img style="width: 100%; margin: 0; padding: 0; display: block;" class="wave" src="../../assets/img/waveFinal.png" alt="">
  </div>
</template>

<script setup>
import { useWindowSize } from '@vueuse/core';

const { width } = useWindowSize()
</script>

<style scoped>
@import url('../../MediaQueries/Hero.css');

.btns{
  width: 100%;
}

button:nth-child(2){
  border: solid 2px white;
  background-color: transparent;
  color: white;
}
button{
  width: 100%;
  padding: 1rem;
  border-radius: 0.5rem;
  background-color: white;
  border: none;
  color: black;

  font-size: 1.1rem;
  font-family: 'Inter';
  font-weight: 600;
}

.container{
  width: 100vw;
  height: 55vh;
  background-color: var(--primary-color);
  padding-inline: 0rem;
  z-index: 10;
}

.wrapper{
  width: 100%;
  height: 100%;

  display: flex;
  flex-direction: column;
  align-items: flex-start;
  justify-content: center;
  max-width: 1440px;
  padding-inline: 2rem;
  margin-inline: auto; /* questo lo centra */
}

.texts{
  width: 100%;
  height: 100%;
  box-sizing: border-box;

  display: flex;
  flex-direction: column;
  align-items: flex-start;
  justify-content: center;
  margin-top: .5rem;
  gap: 1.5rem;
}

h1{
  font-family: 'Inter';
  font-size: 3rem;
  font-weight: 700;
  color: white;
  line-height: 1;
}

p{
  font-size: 0.9rem;
  font-weight: 200;
  color: rgb(211, 255, 211);
  font-family: Inter, sans-serif;
}

.floating-img {
  animation: float 3s ease-in-out infinite;
  position: absolute;
  width: 75%;

  left: 50%;
  transform: translateX(-50%);
  z-index: 100;
}

@keyframes float {
  0%   { transform: translateX(-50%) translateY(0); }
  50%  { transform: translateX(-50%) translateY(-3rem); }
  100% { transform: translateX(-50%) translateY(0); }
}

</style>
