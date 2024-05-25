<script setup>
import Components from "./components/content.vue"

// const isAdmin = ref(true)
</script>

<template>
  <!-- <component :is="isAdmin ? Admin : Editor" /> -->
  <component :is="Components" />
  <!-- <PDF /> -->
  <!-- <Heard /> -->
</template>
