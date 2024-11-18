<script setup>
import { ref } from 'vue';

const nValue2 = ref(0);
const result3 = ref("");


function GregoryLeibniz() {
  let piApproximation = 0;
  let sign = 1;

  for (let i = 1; i <= nValue2.value; i++) {
    piApproximation += sign / (2 * i - 1);
    sign *= -1;
  }

  result3.value = (4 * piApproximation).toFixed(6);
}
</script>

<template>
  <div class="calculator-box">
    <form @submit.prevent="GregoryLeibniz">
      <h2>Gregory-Leibniz Calculator</h2>
      <label>n Value:</label>
      <input v-model="nValue2" type="number" />
      <label>Approximation of Pi:</label>
      <input v-model="result3" type="text" readonly />
      <button type="submit">Calculate</button>
    </form>
  </div>
</template>

<style scoped>

.calculator-box {
  background-color: #ffffff;
  border-radius: 10px;
  padding: 20px;
  margin: 10px;
  box-shadow: 0 4px 15px rgba(0, 0, 0, 0.1);
  transition: transform 0.3s;
  flex: 1 1 300px;
  max-width: 400px;
  display: flex;
  flex-direction: column;
  align-items: center;
}

.calculator-box:hover {
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

/* Focused input fields */
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
