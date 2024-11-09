<script setup>
import { ref } from 'vue';

const emit = defineEmits(['update:operation']);
const localOperation = ref('+');

function updateOperation() {
  emit('update:operation', localOperation.value);
}
</script>

<template>
    <div class="mb-4">
      <label for="operation" class="form-label">Operação</label>
      <select v-model="localOperation" @change="updateOperation" class="form-select" id="operation">
        <option value="+">Soma</option>
        <option value="-">Subtração</option>
        <option value="*">Multiplicação</option>
        <option value="/">Divisão</option>
      </select>
    </div>
  </template>
  

  