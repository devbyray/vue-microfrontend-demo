<script setup lang="ts">
import { storeToRefs } from "pinia";
import { useStore } from "../stores/counter";
const store = useStore();
const { count } = storeToRefs(store);
</script>

<template>
  <button class="counter" @click="store.increment">
    Host counter: {{ count }}
  </button>
</template>

<style scoped>
.counter {
  border: 0 solid #e2e8f0;
  margin-top: 10px;
  background-color: rgb(109, 246, 82);
  border-radius: 0.25rem;
  font-weight: 700;
  padding: 0.5rem 1rem 0.5rem 1rem;
  color: rgb(24, 24, 24);
}
</style>
