<template>
  <div class="card">
    <h1>${{ props.price }}</h1>
    <div class="line"></div>
    <div class="specs">
      <Spec icon="fluent:checkmark-12-filled" :spec="cards[props.cardsNumber].a" class="specs"/>
      <Spec icon="fluent:checkmark-12-filled" :spec="cards[props.cardsNumber].b" class="specs"/>
      <Spec icon="fluent:checkmark-12-filled" :spec="cards[props.cardsNumber].c" class="specs"/>
      <Spec icon="fluent:checkmark-12-filled" :spec="cards[props.cardsNumber].d" class="specs"/>
      <Spec icon="fluent:checkmark-12-filled" :spec="cards[props.cardsNumber].e" class="specs"/>
    </div>
  </div>
</template>

<script setup>
import cards from '@/constants/PriceCards.js'

const props = defineProps({
  cardsNumber: Number,
  price: Number
})
</script>

<style scoped>
@import url('../MediaQueries/PriceCard.css');
  .card{
    width: 100%;
    height: 30rem;

    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: flex-start;
    gap: 1rem;
    background-color: rgb(255, 255, 255);
    border: solid 2px rgb(0, 0, 0);
    border-radius: 0.85rem;
    box-shadow: 4px 4px 4px 4px rgb(32, 196, 73);
    padding: 2rem;
    scroll-snap-align: start;
    flex: 0 0 auto;
  }

  h1{
    font-family: 'Inter';
    font-size: 3.5rem;
    font-weight: 800;
  }

  .line{
    width: 100%;
    height: 0.2vh;

    background-color: rgb(212, 212, 212);
    border-radius: 2rem;
  }

  .specs{
    width: 100%;
    height: 100%;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
  }
</style>
