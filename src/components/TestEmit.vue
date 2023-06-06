<script setup lang="ts">
import { ref } from "vue";
// BEFORE
//const emit = defineEmits(['increment', 'delete']);
// const emit = defineEmits<{
//   (e: 'increment', id: number): void
//   (e: 'update', value: string): void
// }>()

// After
const emit = defineEmits<{
  increment: [id: number]; // named tuple syntax
  update: [value: string];
}>();
</script>

<template>
  <h2>emit component</h2>
  <button @click="emit('increment', 2)">increment</button>
</template>
