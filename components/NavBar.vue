<template>
  <div class="contenitore">
    <nav>
      <h1>WebGo</h1>
      <div v-show="width > 768" class="links">
        <NuxtLink class="HLink" to="/">Home</NuxtLink>
        <NuxtLink class="HLink" to="/about">About</NuxtLink>
        <NuxtLink class="HLink" to="/contact">Contact</NuxtLink>
      </div>

      <aside v-show="width < 768" :class="`${isExpanded ? 'is-expanded' : ''}`">
        <div class="wrapper">
          <button style="background-color: transparent; border: none; width: 50px; height: 50px;" @click="toggleAside">
            <icon style="color: black; font-size: 1rem;" name="material-symbols:menu-rounded"/>
          </button>
        </div>
        <NuxtLink v-show="isExpanded" to="/" class="link">Home</NuxtLink>
        <NuxtLink v-show="isExpanded" to="/about" class="link">About</NuxtLink>
        <NuxtLink v-show="isExpanded" to="/contact" class="link">Contact</NuxtLink>
      </aside>


    </nav>
  </div>
</template>

<script setup>
import { NuxtLink } from '#components';
import { useWindowSize } from '@vueuse/core'
import { ref } from 'vue'

const isExpanded = ref(false);
const { width } = useWindowSize()

const toggleAside = () => {
  isExpanded.value = !isExpanded.value;
}


</script>

<style scoped>
@import url('../MediaQueries/NavBar.css');

  aside{
    min-height: 100vh;

    width: 4rem;
    transition: 0.4s ease-out;

    position: absolute;
    right: 0;
    top: 0;
    display: flex;
    flex-direction: column;
    align-items: flex-end;
    z-index: 300;
  }

  .is-expanded{
      width: 70vw !important;
      background-color: rgb(239, 239, 239);
    }

    .wrapper{
      transition: 0.4s ease-out;
      width: 4rem;
      background-color:  transparent;
      display: flex;
      align-items: center;
      justify-content: flex-start;
    }



  div{
    width: 100vw;
    height: 15vh;
    background-color: white;

    display: flex;
    align-items: center;
    justify-content: center
  }

  nav{
    width: 100%;
    max-width: 1440px;
    height: 100%;

    display: flex;
    align-items: center;
    justify-content: space-between;

    padding-inline: 2rem;

  }

  h1{
    width: 50%;
    height: 100%;

    display: flex;
    align-items: center;
    justify-content: flex-start;

    font-family: Inter, sans-serif;
    font-size: 1.5rem;
    font-style: italic;
    font-weight: 500;
  }
  button{
    transition: 0.4s ease-out;
  }



  .contenitore{
    box-shadow: 0px 4px 8px rgb(9, 166, 0);
    position: static;
    z-index: 1000;
  }

  .links{
    width: 30%;
    height: 100%;

    display: flex;
    align-items: center;
    justify-content: space-between;
  }

  .HLink{
    font-size: 1.2rem;
    font-family: Inter, sans-serif;
    font-weight: 500;
    text-decoration: none;
    color: rgb(68, 68, 68);
    transition: 0.4s ease-out;
  }

  .HLink:last-child{
    border-radius: 0.5rem;
    border: solid 2px var(--primary-color);
    background-color: white;
    color: var(--primary-color);
    padding-inline: 1.5rem;
    padding-block: 0.75rem;
  }
  .HLink:last-child:hover{

    background-color: var(--primary-color);
    color: white;
  }

  .HLink:hover{
    scale: 1.05;
    color: black;
  }

  .link{

    width: 100%;
    padding-inline: 2rem;
    height: 7vh;
    border-top: solid 1px rgb(225, 225, 225);

    display: flex;
    align-items: center;

    font-size: 1.2rem;
    font-family: Inter, sans-serif;
    font-weight: 500;
    text-decoration: none;
    color: black;
    transition: 0.4s ease-out;

  }

  .link:hover{

    scale: 1.05;
    cursor: pointer;
  }
</style>
