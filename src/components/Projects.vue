<script setup lang="ts">
import Project from "@/components/Project.vue";
import json from '@/json/projects.json'
import {onMounted, ref} from "vue";
import type {ProjectType} from "@/components/ProjectInterface";

let categories: { [category: string]: ProjectType[]} = {}
const projects: { [id: string]: ProjectType } = json

let divLoaded = ref(false)

onMounted(() => {
  for (const id in projects) {
    const project = projects[id];
    if (categories && categories[project.category]) {
      categories[project.category].push(project);
    } else {
      categories[project.category] = [project];
    }
  }

  divLoaded.value = true
  console.log(divLoaded, categories)
})

</script>

<template>
  <div class="container-sm">
    <div class="flex h-flex-center title">
      <h1 class="text-xxl">Projects</h1>
    </div>
    <div class="projects">
      <h1 class="subtitle text-xl">// Websites</h1>
      <div class="project-render">
        <div class="project-row">
          <template v-if="divLoaded">
            <div class="project" v-for="project in categories.website">
              <Project
                  :name="project.name"
                  :description="project.summary"
                  :link="project.link"
                  :display_link="project.display_link"
                  :technologies="project.technologies"
              />
            </div>
          </template>
        </div>
      </div>
      <h1 class="subtitle text-xl">// Python and Java/Kotlin Projects</h1>
      <div class="project-row">
        <template v-if="divLoaded">
          <div class="project" v-for="project in categories.python">
            <Project
                :name="project.name"
                :description="project.summary"
                :link="project.link"
                :display_link="project.display_link"
                :technologies="project.technologies"
            />
          </div>
        </template>
        <template v-if="divLoaded">
          <div class="project" v-for="project in categories.kotlin">
            <Project
                :name="project.name"
                :description="project.summary"
                :link="project.link"
                :display_link="project.display_link"
                :technologies="project.technologies"
            />
          </div>
        </template>
      </div>
      <h1 class="subtitle text-xl">// Browser Extensions</h1>
      <div class="project-row">
        <template v-if="divLoaded">
          <div class="project" v-for="project in categories.extension">
            <Project
                :name="project.name"
                :description="project.summary"
                :link="project.link"
                :display_link="project.display_link"
                :technologies="project.technologies"
            />
          </div>
        </template>
      </div>
    </div>
  </div>
</template>

<style scoped>
.title {
  margin: 50px 0;
}

.subtitle {
  margin: 0 30px;
}

.subtitle:not(:nth-child(1)) {
  margin: 30px;
}

.projects {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
}

.project-row {
  display: flex;
  margin: 30px 0;
}

@media screen and (max-width: 768px) {
  .project-row {
    display: flex;
    flex-direction: column;
    margin: 0;
  }

  .subtitle {
    font-size: 2rem;
    margin-top: 10px;
  }
}

</style>