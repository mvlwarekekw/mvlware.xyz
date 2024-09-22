<script setup lang="ts">
import { RouterView } from 'vue-router'
import Navbar from "@/components/Navbar.vue";
import GradientBar from "@/components/GradientBar.vue";
import { inject } from "@vercel/analytics";

inject()
</script>

<template>
  <Navbar />
  <RouterView />
  <GradientBar />
</template>

<style scoped>

</style>
