<script setup lang="ts">
import json from "@/json/projects.json";
import type {ProjectType} from "@/components/ProjectInterface";
import Technology from "@/components/Technology.vue";
import {onMounted, ref} from "vue";

const props = defineProps({
  id: {
    type: String,
    default: "1"
  }
})

const projects: { [id: string]: ProjectType } = json
const project = projects[props.id]

const last_project = ref(0)
const next_project = ref(0)

const project_id = parseInt(props.id)

onMounted(() => {
  last_project.value = (project_id - 1)
  next_project.value = (project_id + 1)
})

const technology_name = (path: String) => {
  const technology = (path as string)
      .replace('/', '')
      .replace('.svg', '')

  return technology.charAt(0).toUpperCase() + technology.slice(1)
}
</script>

<template>
<div class="container">
  <div class="flex">
    <div class="details">
      <div class="flex flex-column summary">
        <div class="title">
          <h1 class="text-xl">{{ project.name }}</h1>
        </div>
        <div class="technologies">
          <div v-for="technology in project.technologies" class="technology-wrapper">
            <Technology
                :name="technology_name(technology)"
                :path="technology"
                class="technology"
            />
          </div>
        </div>
        <div class="description">
          <p class="text-md">{{ project.summary }}</p>
        </div>
      </div>
      <div class="description">
        <p class="text-md">{{ project.description }}</p>
      </div>
      <div class="links">
        <div class="p text-md text-white">// Links</div>
        <div class="flex flex-row">
          <a :href="project.github" target="_blank" rel="noopener noreferrer" class="flex flex-row v-flex-center">
            <img src="/github-light.svg" alt="" class="icon">
            <p class="">GitHub</p>
          </a>
          <a :href="project.link" class="flex flex-row v-flex-center">
            <img src="/opentab.svg" alt="" class="icon">
            <p class="">{{ project.display_link }}</p>
          </a>
        </div>
      </div>
      <div class="screenshots">
        <img v-for="ss in project.screenshots" :src="ss" alt="project screenshot" class="screenshot">
      </div>
    </div>
  </div>
  <div class="arrows">
    <div class="arrow-left" v-if="project_id > 1">
      <a :href="`/project/${last_project}`">
        <div class="flex flex-row v-flex-center">
          <img src="/arrow.svg" alt="" class="arrow">
          <p class="c-font-size">Last Project</p>
        </div>
      </a>
    </div>
    <div class="arrow-right" v-if="project_id < 4">
      <a :href="`/project/${next_project}`">
        <div class="flex flex-row v-flex-center">
          <p class="c-font-size">Next Project</p>
          <img src="/arrow.svg" alt="" class="arrow">
        </div>
      </a>
    </div>
  </div>
</div>
</template>

<style scoped>
.container {
  margin-left: 150px;
}

.container > div {
  align-items: center;
  justify-content: center;
}

.summary {
  margin-top: 100px;
  border: #606060 solid 1px;
  border-radius: 15px;
  padding: 20px;
}

.title {
  display: flex;
  flex-direction: column;
}

.text-xl {
  font-size: 3.7rem;
  font-weight: 500;
}

.technologies {
  display: flex;
}

.technology-wrapper {
  display: flex;
  margin-right: 20px;
}

.details {
  max-width: 28vw;
}

.description {
  display: flex;
  flex-direction: column;
  margin-top: 30px;
}

.description p {
  color: #909090;
}

.text-white {
  color: #fff;
  margin-bottom: 10px;
}

.links {
  margin-top: 40px;
  display: flex;
  flex-direction: column;
}

.links p {
  font-size: 1.5rem;
  margin-left: 20px;
  padding-right: 8px;
}

.links a {
  margin-bottom: 20px;
  margin-right: 25px;
  border: #fff solid 1px;
  border-radius: 6px;
  padding: 10px;
}

.icon {
  width: 1.5vw;
}

.screenshots {
  display: flex;
  flex-direction: column;
  justify-items: auto;
}

.screenshot {
  border: #fff solid 1px;
  border-radius: 6px;
  width: 30vw;
  margin-bottom: 20px;
}

.arrow {
  width: 2.3vw;
}

.arrow:nth-child(1) {
  transform: rotate(180deg);
}

.c-font-size {
  font-size: 1.7rem;
  padding: 0 15px;
}

.arrow-left {
  position: absolute;
  bottom: 40px;
  left: 40px;
}

.arrow-right {
  position: absolute;
  bottom: 40px;
  right: 40px;
}

</style>