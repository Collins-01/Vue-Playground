<script setup lang="ts">
import { ref } from 'vue'

defineProps<{ msg: string }>()

const count = ref(0)

const increaseCount = () => {
  count.value++;
  if (count.value > 10) {
    count.value = 10;
  }
  console.log(count.value);
}
const decreaseCount = () => {
  count.value--;
  if (count.value < 0) {
    count.value = 0;
  }
}
</script>

<template>
  <h1>{{ msg }}</h1>

  <div class="card">
    <p>The current count is {{ count }}</p>
    <div class="button-row">
      <button type="button" @click="increaseCount">Increase</button>
      <button type="button" @click="decreaseCount">Decrease</button>
    </div>

  </div>
</template>

<style scoped>
.read-the-docs {
  color: #888;
}

.button-row {
  display: flex;
  gap: 1rem;
}
.button-row button {
  padding: 0.5rem 1rem;
  background-color: #42b883;
  color: white;
  border: none;
  border-radius: 4px;
  cursor: pointer;
}
.button-row button:hover {
  background-color: #35495e;
}
.button-row button:active {
  background-color: #42b883;
}
.button-row button:disabled {
  background-color: #ccc;
  cursor: not-allowed;
}
.button-row button:disabled:hover {
  background-color: #ccc;
}
.button-row button:disabled:active {
  background-color: #ccc;
}
.button-row button:disabled:focus {
  outline: none;
}
.button-row button:focus {
  outline: 2px solid #42b883;
}
</style>
