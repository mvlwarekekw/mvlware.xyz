<script setup lang="ts">

import Project from "@/components/Project.vue";
</script>

<template>
  <div class="container-sm">
    <div class="flex h-flex-center title">
      <h1 class="text-xxl">Projects</h1>
    </div>
    <div class="projects">
      <div class="project-row">
        <Project
            name="IskraMC"
            description="IskraMC is a minecraft minigame server network currently in development."
            :technologies="['/kotlin.svg', '/mongodb.svg']"
        />
        <Project
            name="Personal Website"
            description="My personal Website (the website you are on at this moment)"
            link="https://mvlware.xyz"
            display_link="mvlware.xyz"
            :technologies="['/vuejs.png']"
        />

        <Project
            name="fuck distractions"
            description="A chrome extension that automatically blocks yt shorts, instagram and tiktok. :D"
            link="https://github.com/mvlwarekekw/fuckDistractions"
            display_link="GitHub"
            :technologies="['/js.png']"
        />
      </div>
      <div class="project-row">
        <Project
            name="pytwitter"
            description="Python wrapper for the Twitter API, development paused because Im unable to test the API."
            link="https://github.com/mvlwarekekw/pytwitter"
            display_link="GitHub"
            :technologies="['/python.png']"
        />
      </div>
    </div>
  </div>
</template>

<style scoped>
.title {
  margin: 50px 0;
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
}

</style>