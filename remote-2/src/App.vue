<script setup lang="ts">
import { state } from "shared";
import Counter from "./components/Counter.vue";
import enviroment from "./enviroment";
import image from "./remote_assets/logo.svg";
console.log("remote got message:", state.message);
console.info("vite import.meta got message:", enviroment.VITE_EXAMPLE);
</script>

<template>
  <div
    style="
      background: #ccc;
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
    <div style="margin-top: 10px; font-size: 25px">I'm the remote-2 app</div>
    <Counter />
  </div>
</template>

<style scoped />
