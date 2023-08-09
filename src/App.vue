<script setup lang="ts">
import { appWindow } from "@tauri-apps/api/window";

function closeWindow() {
  appWindow.close();
}

function toggleMaximize() {
  appWindow.toggleMaximize();
}

function minimizeWindow() {
  appWindow.minimize();
}
</script>

<template>
  <div class="w-full h-screen rounded-t-xl bg-slate-50">
    <div
      class="w-full h-11 relative rounded-t-lg bg-blue-900 flex overflow-hidden justify-start items-center space-x-1.5 px-2"
    >
      <div
        data-tauri-drag-region
        @dblclick="toggleMaximize"
        class="absolute inset-0 w-full h-full bg-black opacity-50"
      ></div>
      <span
        @click="closeWindow"
        class="relative w-3 h-3 border-2 border-red-400 rounded-full hover:bg-red-400"
      ></span>
      <span
        @click="toggleMaximize"
        class="relative w-3 h-3 border-2 border-yellow-400 rounded-full hover:bg-yellow-400"
      ></span>
      <span
        @click="minimizeWindow"
        class="relative w-3 h-3 border-2 border-green-400 rounded-full hover:bg-green-400"
      ></span>
    </div>
  </div>
</template>
