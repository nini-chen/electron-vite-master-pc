<script setup>
import PDF from "./components/content.vue"

// const isAdmin = ref(true)
</script>

<template>
  <!-- <component :is="isAdmin ? Admin : Editor" /> -->
  <component :is="PDF" />
  <!-- <PDF /> -->
  <!-- <Heard /> -->
</template>
