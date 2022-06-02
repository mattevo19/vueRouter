<template>
  <div class="card">
    <img :src="`/images/${experience.image}`" alt="experience.name" />
    <span class="card__text">
      {{ experience.name }}
    </span>
  </div>
</template>

<script lang="ts" setup>
import { ref } from "vue"

const props = defineProps({
  experience: {
    type: Object,
    required: true
  }
})

const experience = ref(props.experience)
</script>
