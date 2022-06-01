<script setup lang="ts">
import { RouterLink, RouterView } from "vue-router"
import NavComp from "./components/NavComp.vue"
</script>

<template>
  <div class="container">
    <header></header>
    <NavComp />
    <RouterView />
  </div>
</template>

<style></style>
