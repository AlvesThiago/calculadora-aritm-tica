<script setup>
import { ref, computed } from 'vue';
import NumberInput from './components/NumberInput.vue';
import OperationSelector from './components/OperationSelector.vue';
import ResultDisplay from './components/ResultDisplay.vue';

const number1 = ref(0);
const number2 = ref(0);
const operation = ref('+');

const result = computed(() => {
  switch (operation.value) {
    case '+':
      return number1.value + number2.value;
    case '-':
      return number1.value - number2.value;
    case '*':
      return number1.value * number2.value;
    case '/':
      return number2.value !== 0 ? number1.value / number2.value : 'Erro: Divisão por zero';
    default:
      return 0;
  }
});
</script>

<template>
  <div class="container mt-5">
    <div class="card p-4">
      <h2 class="text-center mb-4">Calculadora Aritmética</h2>

      <NumberInput @update:number1="number1 = $event" @update:number2="number2 = $event" />

      <OperationSelector @update:operation="operation = $event" />
      
      <ResultDisplay :result="result" />
    </div>
  </div>
</template>


