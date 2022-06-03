<script lang="ts" setup>
import { computed, ref, watchPostEffect } from "vue"
import { useRoute } from "vue-router"
import sourceData from "@/data.json"

import GoBack from "@/components/GoBack.vue"
import ExperienceCard from "@/components/ExperienceCard.vue"

const route = useRoute()
// const destination = ref(null)

const props = defineProps({
  id: {
    type: Number,
    required: true
  }
})

const destination = computed(() => {
  return sourceData.destinations.find((destination) => destination.id === props.id)
})

// watchPostEffect(async () => {
//   try {
//     const res = await fetch(`https://travel-dummy-api.netlify.app/${route.params.slug}`)
//     destination.value = await res.json()
//   } catch (error) {
//     console.error
//   }
// })
</script>

<template>
  <div>
    <section>
      <h1>{{ destination?.name }}</h1>
      <GoBack />
      <div class="destination-details">
        <img :src="`/images/${destination?.image}`" alt="destination.name" />
        <p>{{ destination?.description }}</p>
      </div>
    </section>
    <section v-if="destination" class="experiences">
      <h2>Top Experiences in {{ destination.name }}</h2>
      <div class="cards">
        <router-link
          v-for="experience in destination.experiences"
          :key="experience.slug"
          :to="{ name: 'experience.show', params: { experienceSlug: experience.slug } }"
        >
          <ExperienceCard :experience="experience" />
        </router-link>
      </div>
      <router-view />
    </section>
  </div>
</template>
