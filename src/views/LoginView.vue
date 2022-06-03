<script lang="ts" setup>
import { useRouter } from "vue-router"
import { ref } from "vue"

const router = useRouter()

const username = ref("")
const password = ref("")

const login = () => {
  // this is where you would auth user against api
  window.user = username.value
  router.push({ name: "protected" })
}
</script>

<template>
  <div class="login">
    <form class="form" @submit.prevent="login">
      <h1>Login</h1>
      <label for="username">Username</label>
      <input type="text" v-model="username" name="username" class="input" />

      <label for="password">Password</label>
      <input type="text" v-model="password" name="password" class="input" />

      <button class="btn">Login</button>
    </form>
  </div>
</template>
