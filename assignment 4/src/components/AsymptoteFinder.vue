<script setup>
import { ref } from 'vue';

const nValue1 = ref(0);
const mValue = ref(0);
const result = ref("");

function Asymptote() {
  let Result = ""; 

  if (mValue.value === nValue1.value) {
    result.value = "The asymptote is horizontal";
  } else if (nValue1.value > mValue.value) {
    result.value = "The asymptote is the x-axis";
  } else if (mValue.value > nValue1.value) {
    if ((mValue.value - nValue1.value) === 1) {
      result.value = "Linear";
    } else if ((mValue.value - nValue1.value) === 2) {
      result.value = "Quadratic";
    } else if ((mValue.value - nValue1.value) === 3) {
      result.value = "Cubic";
    } else if ((mValue.value - nValue1.value) === 4) {
      result.value = "Quartic";
    } else if ((mValue.value - nValue1.value) === 5) {
      result.value = "Quintic";
    } else if ((mValue.value - nValue1.value) === 6) {
      result.value = "Sextic";
    } else if ((mValue.value - nValue1.value) === 7) {
      result.value = "Septic";
    } else if ((mValue.value - nValue1.value) === 8) {
      result.value = "Octic";
    } else if ((mValue.value - nValue1.value) === 9) {
      result.value = "Nonic";
    } else if ((mValue.value - nValue1.value) === 10) {
      result.value = "Decic";
    }
  }
}
</script>

<template>
    <div class="Asymptote">
        <form @submit.prevent="Asymptote">
            <h2>Asymptote Calculator</h2>
            <label>m Value:</label>
            <input v-model="mValue" type="number" />
            <label>n Value:</label>
            <input v-model="nValue1" type="number" />
            <label>Asymptote Type (Result):</label>
            <input v-model="result" type="text" readonly />
            <button type="submit">Calculate</button>
        </form>
    </div>
</template>

<style scoped>
.Asymptote {
  background-color: #ffffff;
  border-radius: 10px;
  padding: 20px;
  margin: 10px;
  box-shadow: 0 4px 15px rgba(0, 0, 0, 0.1);
  transition: transform 0.3s;
  flex: 1 1 300px;
}

.Asymptote:hover {
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
