<script setup lang="ts">
import { RouterView } from "vue-router"

import NavComp from "./components/NavComp.vue"
</script>

<template>
  <NavComp />
  <div class="container">
    <RouterView v-slot="{ Component }">
      <transition name="fade" mode="out-in">
        <component :is="Component" :key="$route.path"></component>
      </transition>
    </RouterView>
  </div>
</template>

<style>
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.6s;
}

.fade-enter,
.fade-leave-to {
  opacity: 0;
}
</style>
