<script setup lang="ts">
import { ref } from "vue";
import LiquidGlassVue from "./../../src/index";
const list = ref<string[]>([]);
for (let i = 0; i < 5; i++) {
  list.value.push(new URL(`./assets/${i}.jpg`, import.meta.url).href);
}
</script>
<template>
  <div class="w-full h-auto flex flex-col justify-center items-start">
    <img
      class="w-full h-[600px] object-cover"
      v-for="src in list"
      :src
      alt=""
    />
    <LiquidGlassVue
      style="
        width: 300px;
        padding: 16px;
        border-radius: 4px;
        position: fixed;
        top: 200px;
        left: calc(50% - 150px);
        border-radius: 1rem;
      "
      @click="() => {
        console.log('LiquidGlassVue clicked');
      }"
    >
      <div class="w-[300px] padding-4 color-white">
        <h2>VUE VITE</h2>
        <p>
          This is a simple example of using LiquidGlassVue in a Vue application.
          You can customize the properties to achieve different effects.
        </p>
        <p>
          The component uses a displacement map to create a liquid glass effect.
          You can change the image source to see different results.
        </p>
      </div>
    </LiquidGlassVue>
  </div>
  <div id="control-panel" class="position-fixed h-[100vh] w-[300px] top-0 right-0">

  </div>

</template>

<style scoped></style>
