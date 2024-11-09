<script setup>
import { ref } from 'vue';

const emit = defineEmits(['update:number1', 'update:number2']);
const localNumber1 = ref(0);
const localNumber2 = ref(0);

function updateNumbers() {
  emit('update:number1', localNumber1.value);
  emit('update:number2', localNumber2.value);
}
</script>


<template>
    <div>
      <div class="mb-3">
        <label for="number1" class="form-label">Número 1</label>
        <input type="number" v-model.number="localNumber1" @input="updateNumbers" class="form-control" id="number1" placeholder="Digite o primeiro número" />
      </div>
      <div class="mb-3">
        <label for="number2" class="form-label">Número 2</label>
        <input type="number" v-model.number="localNumber2" @input="updateNumbers" class="form-control" id="number2" placeholder="Digite o segundo número" />
      </div>
    </div>
  </template>
  
