<script setup>
import CosineLaw from "'./components/Pythagorean.vue';" it links to conesine
</script>

<template>
    <div class="CosineLaw">
        <h2>Cosine Law Calculator</h2>
        <label for="sideA">Length of side A:</label>
        <input type="number" id="sideA" placeholder="">
            
        <label for="sideB">Length of side B:</label>
        <input type="number" id="sideB" placeholder="">
            
        <label for="angleC">Angle C (degrees):</label>
        <input type="number" id="angleC" placeholder="">
            
        <label for="result">Result:</label>
        <input type="number" id="result" placeholder="" readonly>
            
        <button id="calculateButton" type="button">Calculate</button>
    </div>
    <div class="Asymptote">
        <h2>Asymptote Calculator</h2>
        <label for="nValue1">n Value:</label>
        <input type="number" id="nValue1" placeholder="">
            
        <label for="mValue">m Value:</label>
        <input type="number" id="mValue" placeholder="">
            
        <label for="result2">Result:</label>
        <input type="text" id="result2" placeholder="" readonly>
            
        <button id="calculateButton1" type="button">Calculate</button>
    </div>
</template>

<style scoped>

</style>
