<script setup lang="ts">
import { RouterView } from 'vue-router'
import Navbar from "@/components/Navbar.vue";
import GradientBar from "@/components/GradientBar.vue";
import { inject } from "@vercel/analytics";
import { injectSpeedInsights } from "@vercel/speed-insights";

inject()
injectSpeedInsights()
</script>

<template>
  <Navbar />
  <RouterView />
  <GradientBar />
</template>

<style scoped>

</style>
