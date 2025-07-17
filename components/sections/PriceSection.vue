<template>
  <div class="container">
    <button @click="scrollLeft">◀</button>

    <div ref="carousel" class="wrapper">
      <PriceCard price="399" cards-number="0" />
      <PriceCard price="599" cards-number="1" />
      <PriceCard price="799" cards-number="2" />
    </div>

    <button @click="scrollRight">▶</button>
  </div>
</template>

<script setup>
import PriceCard from '../PriceCard.vue'
import { ref, nextTick, onMounted } from 'vue'

const carousel = ref(null)
const cardWidth = ref(0)

onMounted(() => {
  nextTick(() => {
    const firstCard = carousel.value?.children[0]
    if (firstCard) {
      cardWidth.value = firstCard.offsetWidth + 16 // Include spazio tra card se necessario
    }
    console.log('🎯 cardWidth:', cardWidth.value)
  })
})

const scrollRight = () => {
  if (carousel.value && carousel.value.scrollBy) {
    carousel.value.scrollBy({ left: cardWidth.value, behavior: 'smooth' })
  }
}

const scrollLeft = () => {
  if (carousel.value && carousel.value.scrollBy) {
    carousel.value.scrollBy({ left: -cardWidth.value, behavior: 'smooth' })
  }
}
</script>

<style scoped>
@import url('../../MediaQueries/PriceSection.css');

.container {
  background-color: var(--primary-color);
  width: 100vw;
  height: auto;
  overflow: hidden;


  display: flex;
  align-items: center;
  justify-content: center;
  gap: 1rem;
  padding: 2rem;
}

.wrapper {
  width: 300%;
  height: 100%;
  display: flex;
  align-items: center;
  gap: 1rem;



  overflow-x: auto;
  scroll-snap-type: x mandatory;
  -webkit-overflow-scrolling: touch;
  scroll-behavior: smooth;
}

.wrapper::-webkit-scrollbar{
  display: none;
}

button {
  width: 8vh;
  height: 8vh;
  border-radius: 50%;
  background-color: white;
  color: black;
  border: solid 1px rgb(205, 205, 205);
  box-shadow: 0px 0px 4px 1px rgb(198, 204, 198);
  font-size: 1.2rem;
  border: none;
  cursor: pointer;
  position: absolute;
  right: 0;
  z-index: 100;
}

button:nth-child(1){
  left: 0;
}

</style>
