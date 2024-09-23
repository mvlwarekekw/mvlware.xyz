<script setup lang="ts">

import Project from "@/components/Project.vue";
</script>

<template>
  <div class="container-sm">
    <div class="flex h-flex-center title">
      <h1 class="text-xxl">Projects</h1>
    </div>
    <div class="projects">
      <Project
          name="IskraMC"
          description="IskraMC is a minecraft minigame server network currently in development."
          :technologies="['/src/assets/kotlin.svg', '/src/assets/mongodb.svg']"
      />
      <Project
          name="Personal Website"
          description="My personal Website"
          link="https://mvlware.xyz"
          display_link="mvlware.xyz"
          :technologies="['/src/assets/vuejs.png']"
      />
      <Project
          name="pytwitter"
          description="Python wrapper for the Twitter API, in dev stages."
          link="https://github.com/mvlwarekekw/pytwitter"
          display_link="Github"
          :technologies="['/src/assets/python.png']"
      />
    </div>
  </div>
</template>

<style scoped>
.title {
  margin: 50px 0;
}

.projects {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
}

</style>