<script setup lang="ts">
import Technology from "@/components/Technology.vue";

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

const technology_name = (path: String) => {
  const technology = (path as string)
      .replace('/', '')
      .replace('.svg', '')

  return technology.charAt(0).toUpperCase() + technology.slice(1)
}
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
    <div class="wrapper flex flex-row technologies">
      <div class="technology-wrapper-title">
        <p class="c-font-size mr">Technologies:</p>
      </div>
      <div v-for="technology in technologies" class="technology-wrapper">
        <Technology v-bind:name="technology_name(technology)" v-bind:path="technology" />
      </div>
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

.technologies {
  display: flex;
  flex-wrap: wrap;
}

.technology-wrapper {
  display: flex;
  align-items: center;
  border: 3px #fff;
  margin-right: 15px;
  margin-bottom: 5px;
}

.technology-wrapper-title {
  display: flex;
  align-items: center;
}

.mr {
  margin-right: 15px;
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

  .technology-wrapper {
    flex-direction: column;
  }

  .technologies {
    text-align: left;
  }
}

</style>