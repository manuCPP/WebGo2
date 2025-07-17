<template>
  <div>
      <HeroSection/>
      <BulletSection/>
      <PriceSection/>
  </div>
</template>

<script setup>
import HeroSection from '@/components/sections/HeroSection.vue'
import BulletSection from '@/components/sections/BulletSection.vue'
import PriceSection from '@/components/sections/PriceSection.vue'
</script>

<style scoped>
.container{
  width: 100vw;

}
</style>

