<script setup lang="ts">
import { defineAsyncComponent } from "vue";
import Counter from "./components/Counter.vue";
const RemoteMFE = defineAsyncComponent(
  // @ts-ignore
  () => import("remote/remote-app"),
);
const RemoteMFE2 = defineAsyncComponent(
  // @ts-ignore
  () => import("remote-2/remote-app"),
);
</script>

<template>
  <div class="host">
    <div class="card" data-e2e="APP__CARD">
      <div class="icon">
        <svg
          enable-background="new 0 0 512 512"
          height="512px"
          id="Layer_1"
          version="1.1"
          viewBox="0 0 512 512"
          width="512px"
          xml:space="preserve"
          xmlns="http://www.w3.org/2000/svg"
          xmlns:xlink="http://www.w3.org/1999/xlink"
          data-e2e="STAR__SYMBOL"
        >
          <path
            d="M316.01,199.02L256.134,14.817L196.239,199.02H1.134l158.102,113.324L98.53,496.487l157.604-114.232  l157.585,114.232l-60.687-184.143L511.134,199.02H316.01z M335.084,318.257l42.407,128.63L267.22,366.963l-11.086-8.033  l-11.086,8.033l-110.291,79.923l42.408-128.63l4.353-13.18l-11.289-8.08L59.903,217.909h136.336h13.724l4.242-13.051l41.929-128.957  l41.91,128.957l4.242,13.051h13.724h136.336l-110.327,79.088l-11.27,8.08L335.084,318.257z"
            fill="#37404D"
          />
        </svg>
      </div>
      <div class="title">I'm the host app</div>
      <Counter />
    </div>
    <RemoteMFE v-if="!!RemoteMFE" />
    <RemoteMFE2 v-if="!!RemoteMFE2" />
  </div>
</template>

<style scoped>
.host {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 20px;
  width: 100%;
}
.host .card {
  background: #3178c6;
  box-shadow: 0 0 20px rgba(0, 0, 0, 0.4);
  border-radius: 5px;
  margin: 20px 20px 20px 20px;
  padding: 20px;
  text-align: center;
  color: white;
}

.host .title {
  margin-top: 10px;
  font-size: 25px;
}

.host svg {
  width: 100px;
  height: 100px;
}

.host path {
  fill: #f6b352;
}
</style>
