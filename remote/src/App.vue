<script setup lang="ts">
import { storeToRefs } from "pinia";
import { state } from "shared";
import { reactive, ref } from "vue";
import Counter from "./components/Counter.vue";
import enviroment from "./enviroment";
import image from "./remote_assets/logo.svg";
import { useStore } from "./stores/counter";
const store = useStore();
const { count } = storeToRefs(store);

console.log("remote got message:", state.message);
console.info("vite import.meta got message:", enviroment.VITE_EXAMPLE);
const counterState = ref(0);
const otherState = reactive({ value: 0 });
function updateCounterState() {
  console.log("update decoupled counter:", counterState.value);
  counterState.value++;
  otherState.value++;
  console.log("update reactive otherState:", otherState.value);
}
</script>

<template>
  <div
    style="
      background: #1f2124;
      box-shadow: 0 0 20px rgba(0, 0, 0, 0.4);
      border-radius: 5px;
      margin: 20px 20px 20px 20px;
      padding: 20px;
      text-align: center;
      color: white;
    "
    data-e2e="APP__CARD"
  >
    <div className="icon">
      <img :src="image" alt="" />
    </div>
    <div style="margin-top: 10px; font-size: 25px">I'm the remote app</div>
    <Counter />
    <button @click="updateCounterState">
      De-coupled counter: {{ counterState }}
    </button>
    <p>Current count: {{ counterState }}</p>
    <p>Other state value: {{ otherState.value }}</p>
  </div>
</template>

<style scoped />
