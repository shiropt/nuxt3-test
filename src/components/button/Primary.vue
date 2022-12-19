<script setup lang="ts">
const emit = defineEmits<{ (e: "click"): void }>();
</script>
<template>
  <button @click="emit('click')"><slot /></button>
</template>
<style>
button {
  background: #cce5ff;
  border: none;
  cursor: pointer;
  width: 100px;
  height: 40px;
}
button:hover {
  opacity: 0.8;
}
</style>
