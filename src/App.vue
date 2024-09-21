<script setup lang="ts">
import { RouterView } from 'vue-router'
import Navbar from "@/components/Navbar.vue";
import GradientBar from "@/components/GradientBar.vue";
</script>

<template>
  <Navbar />
  <RouterView />
  <GradientBar />
</template>

<style scoped>

</style>
