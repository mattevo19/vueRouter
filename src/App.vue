<script setup lang="ts">
import { RouterView } from "vue-router"

import NavComp from "./components/NavComp.vue"
</script>

<template>
  <NavComp />
  <div class="container">
    <RouterView />
  </div>
</template>

<style></style>
