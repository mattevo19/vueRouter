<script lang="ts" setup>
import { useRouter } from "vue-router"
const router = useRouter()
const username = window.user
const logout = () => {
  window.user.value = null
  return router.push({ name: "home" })
}
</script>

<template>
  <div>
    <h1>Greetings, {{ username }}</h1>
    <button @click="logout">Logout</button>
  </div>
</template>
