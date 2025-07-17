<template>
  <div class="bullet">
    <div class="headline">
      <div class="circle"><img :src="images[props.img]" alt=""></div>
      <h2>{{ props.title }}</h2>
    </div>
    <p>{{ props.description }}</p>
  </div>
</template>

<script setup>
import img1 from '@/assets/img/best-price.png'
import img2 from '@/assets/img/clock.png'
import img3 from '@/assets/img/customer-service.png'


const images = [img1, img3, img2];
const props = defineProps({
  img: Number,
  title: String,
  description: String
})
</script>

<style  scoped>
  @import url('../MediaQueries/Bullet.css');
  .bullet{
    width: 100%;
    height: 30%;
    background-color: white !important;
    border: solid 1px var(--primary-color);
    box-shadow: 0px 4px 4px rgb(236, 235, 235);

    display: flex;
    flex-direction: column;
    align-items: flex-start;
    justify-content: space-around;

    padding: 1rem;
    border-radius: 1rem;
  }

  .circle{
    width: 7vh;
    height: 7vh;

    background-color: var(--primary-color);
    border-radius: 50%;

    display: flex;
    align-items: center;
    justify-content: center;

  }

  .headline{
    display: flex;
    align-items: center;
    justify-content: flex-start;
    gap: 1rem;
  }

  h2{
    font-family: Inter, sans-serif;
    font-size: 1.2rem;
    font-weight: 600;
  }

  p{
    font-family: Inter, sans-serif;
    font-weight: 400;
    font-size: 1rem;
    color: rgb(147, 147, 147);
  }

  img{
    width: 50%;

  }
</style>
