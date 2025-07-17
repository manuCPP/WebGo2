<template>
  <div class="spec">
    <Icon :name="props.icon" size="2rem" />
    <h4 style="font-size: 1rem;"> {{ props.spec }} </h4>
  </div>
</template>

<script setup>
const props = defineProps({
  icon: String,
  spec: String
})
</script>

<style  scoped>
  .spec{
    width: 100%;
    height: auto;

    display: flex;
    flex-direction: row !important;
    justify-content: flex-start;
    align-items: center;
    gap: 2rem;


  }

  h4{
    width: 80%;


    font-weight: 100;
    font-family: 'Inter';
    font-size: 0.8rem !important;
    color: grey;

    text-wrap: no-wrap;
    margin: 0;
    padding: 0;
    text-align: left;

  }
</style>
