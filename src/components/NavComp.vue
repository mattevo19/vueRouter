<script lang="ts" setup>
import sourceDate from "@/data.json"
const destinations = sourceDate.destinations
</script>

<template>
  <nav id="nav">
    <router-link id="logo" to="/">Travel App</router-link>
    <router-link
      v-for="destination in destinations"
      :key="destination.id"
      :to="{ name: 'destination.show', params: { id: destination.id, slug: destination.slug } }"
    >
      <h3>{{ destination.name }}</h3>
    </router-link>
    <router-link :to="{ name: 'protected' }"><h3>Dashboard</h3></router-link>
  </nav>
</template>
