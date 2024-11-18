<script setup>
import CosineLaw from './components/CosineLaw.vue';
import AsymptoteFinder from './components/AsymptoteFinder.vue';
import GregoryLeibnizPi from './components/GregoryLeibnizPi.vue';
</script>

<template>
  <div class="Calculator">
    <CosineLaw />
    <AsymptoteFinder />
    <GregoryLeibnizPi />
  </div>
  
</template>

<style scoped>
.Calculator {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  gap: 20px;
}
  .Calculator > * {
  flex: 1 1 300px; 
  max-width: 400px; 
  margin: 10px;
}
</style>