<template>
  <div class="container">
    <div class="wrapper">
      <h1>Perché scegliere WebGo</h1>
      <div class="bullets">
        <Bullet img="0" title="Servizi Offerti" description="Dal design alla pubblicazione, creiamo siti veloci, intuitivi e ottimizzati per la tua attività."/>
        <Bullet img="1" title="Prezzi Convenienti" description="Soluzioni web professionali a prezzi accessibili, ideali per startup, freelance e piccole imprese."/>
        <Bullet img="2" title="Contatto Rapido" description="Hai un'idea? Scrivici e in pochi giorni avrai un sito pronto per il tuo business."/>
      </div>
    </div>
  </div>
</template>

<script setup>
import Bullet from '@/components/Bullet.vue'
</script>

<style scoped>
@import url('../../MediaQueries/BulletSection.css');
  .container{
    width: 100vw;
    height: 100vh;
    background-color: white;
    padding-bottom: 2rem;
    margin-top: 18rem;

  }

  .wrapper{
    width: 100%;
    height: 100%;
    max-width: 1440px;
    padding-inline: 2rem;
    margin-inline: auto; /* questo lo centra */

    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: space-evenly;


  }

  h1{
    text-align: center;
    font-family: Inter, sans-serif;
    font-size: 2rem;
    width: 100%;
    margin-bottom: 3rem;

  }

  .bullets{
    width: 100%;
    height: 80%;

    box-sizing: border-box;

    display: flex;
    flex-direction: column;
    justify-content: space-between;
    align-items: center;
  }


</style>
