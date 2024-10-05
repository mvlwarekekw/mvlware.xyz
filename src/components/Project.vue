<script setup lang="ts">
defineProps({
  name: {
    type: String,
    default: "Project"
  },
  description: {
    type: String,
    default: "Project Description"
  },
  link: {
    type: String,
    default: "https://mvlware.xyz/projects"
  },
  display_link: {
    type: String,
    default: "No website"
  },
  technologies: {
    type: Array<string>,
    default: []
  }
})
</script>

<template>
<div class="card">
  <h2 class="text-lg">
    // {{ name }}
  </h2>
  <a target="_blank" rel="noopener noreferrer" :href="link" class="link" >
    <div class="wrapper flex flex-row v-flex-center">
      <img src="/opentab.svg" alt="" class="tab-icon">
      <p class="c-font-size">{{ display_link }}</p>
    </div>
  </a>
  <div class="wrapper">
    <p class="text-md description">
       {{ description }}
    </p>
  </div>
  <div class="wrapper flex flex-row">
    <p class="technologies c-font-size">Technologies:</p>
    <img v-for="technology in technologies" :src="(technology as string)" :alt="technology" class="technology" >
  </div>
</div>
</template>

<style scoped>
.card {
  display: flex;
  flex-direction: column;
  background-color: #191818;
  width: 19vw;
  border-radius: 24px;
  padding: 0 25px;
  margin: 0 30px;
}

.card h2 {
  margin: 25px 0 0;
}

.tab-icon {
  width: 2.3vh;
  height: 2.3vh;
  margin-right: 15px;
}

.link {
  text-decoration: none;
}

.description {
  width: 18vw;
  margin: 17px 0;
}

.technology {
  width: 1.3vmax;
  height: 1.3vmax;
  margin: 0 0 12px 20px;
}

.wrapper:last-child {
  position: relative;
  margin: 15px 0;
}

.c-font-size {
  font-size: 1.3rem;
}

@media screen and (max-width: 768px) {
  .card {
    width: 70%;
    margin: 20px 30px;
  }

  .card h2 {
    font-size: 2rem;
  }

  .description {
    width: 100%;
  }

  .technology {
    width: 4vmax;
    height: 4vmax;
  }
}

</style>