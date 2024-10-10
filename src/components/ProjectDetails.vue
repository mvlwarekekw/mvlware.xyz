<script setup lang="ts">
import json from "@/json/projects.json";

const props = defineProps({
  id: {
    type: String,
    default: "1"
  }
})

interface ProjectType {
  name: string;
  description: string;
  category: string;
  link?: string,
  display_link?: string,
  technologies: any
}

const projects: { [id: string]: ProjectType } = json
const project = projects[props.id]


</script>

<template>
<div class="container">
  <div class="title">
    <h1 class="text-xl">// {{ project.name }}</h1>
  </div>
</div>
</template>

<style scoped>
.title {
  display: flex;
  flex-direction: column;
}
</style>