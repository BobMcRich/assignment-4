<script setup>
import { ref } from 'vue';

const aValue = ref(0);
const bValue = ref(0);
const angleC = ref(0);
const sideC = ref(null);

function calculateSideC() {
  const angleCRadians = angleC.value * (Math.PI / 180);
  sideC.value = Math.sqrt(
    aValue.value ** 2 + bValue.value ** 2 - 2 * aValue.value * bValue.value * Math.cos(angleCRadians)
  ).toFixed(2);
}
</script>

<template>
    <div class="CosineLaw">
        <form @submit.prevent="calculateSideC">
            <h2>Cosine Law Calculator</h2>
            <label for="sideA">Length of side A:</label>
            <input v-model="aValue" type="number" />
            <label for="sideB">Length of side B:</label>
            <input v-model="bValue" type="number" />
            <label for="angleC">Angle C (degrees):</label>
            <input v-model="angleC" type="number" />
            <label for="result">Side C (Result):</label>
            <input v-model="sideC" type="text" readonly />
            <button type="submit">Calculate</button>
        </form>
    </div>
</template>

<style scoped>
.CosineLaw {
  background-color: #ffffff;
  border-radius: 10px;
  padding: 20px;
  margin: 10px;
  box-shadow: 0 4px 15px rgba(0, 0, 0, 0.1);
  transition: transform 0.3s;
  flex: 1 1 300px;
}

.CosineLaw:hover {
  transform: translateY(-5px);
}

h2 {
  font-family: 'Roboto', sans-serif;
  text-align: center;
  color: #333;
  margin-bottom: 10px;
}

label {
  display: block;
  margin: 10px 0 5px;
}

input[type="number"],
input[type="text"] {
  width: calc(100% - 20px);
  padding: 10px;
  margin-bottom: 15px;
  border: 2px solid #ccc;
  border-radius: 5px;
  transition: border-color 0.3s;
}

input[type="number"]:focus,
input[type="text"]:focus {
  border-color: #007bff;
  outline: none;
}

button {
  background-color: #28a745;
  color: white;
  border: none;
  padding: 10px 20px;
  border-radius: 5px;
  cursor: pointer;
  transition: transform 0.2s, background-color 0.3s;
  font-weight: bold;
}

button:hover {
  transform: scale(1.05);
  background-color: #218838;
}

button:active {
  transform: scale(0.95);
}

input[readonly] {
  background-color: #f0f0f0;
}
</style>

        
