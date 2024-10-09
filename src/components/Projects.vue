<script setup lang="ts">
import Project from "@/components/Project.vue";
import json from '@/json/projects.json'
import {onMounted, ref} from "vue";

interface ProjectType {
  name: string;
  description: string;
  category: string;
  link?: string,
  display_link?: string,
  technologies: any
}

let categories: { [category: string]: ProjectType[]} = {}
const projects: { [id: string]: ProjectType } = {
  "1": {
    "name": "Personal Website",
    "description": "My personal Website (the website you are on at this moment)",
    "category":  "website",
    "link": "https://mvlware.xyz",
    "display_link": "mvlware.xyz",
    "technologies": [
      "/vueJS.svg",
      "/typeScript.svg"
    ]
  },
  "2": {
    "name": "pytwitter",
    "description": "Python wrapper for the Twitter API, development paused because Im unable to test the API.",
    "category":  "python",
    "link": "https://github.com/mvlwarekekw/pytwitter",
    "display_link": "GitHub",
    "technologies": ["/python.svg"]
  },
  "3": {
    "name": "IskraMC",
    "description": "IskraMC is a minecraft minigame server network currently in development.",
    "category":  "kotlin",
    "technologies": ["/kotlin.svg", "/mongoDB.svg"]
  },
  "4": {
    "name": "Fuck distractions",
    "description": "A chrome extension that blocks yt shorts, instagram and tiktok websites. :D",
    "category":  "extension",
    "link": "https://github.com/mvlwarekekw/fuckDistractions",
    "display_link": "GitHub",
    "technologies": ["/javaScript.svg"]
  }
}

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
                  :description="project.description"
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
                :description="project.description"
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
                :description="project.description"
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
                :description="project.description"
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