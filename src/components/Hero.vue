<script setup lang="ts">
import {ref} from "vue";
import Skill from "@/components/Skill.vue";

const isSpinning = ref(false)

const spin = () => {
  isSpinning.value = !isSpinning.value
}
</script>

<template>
<section>
  <div class="hero">
    <div class="title">
      <h1 class="text-xxxl">Heya</h1>
      <div class="flex">
        <h1 class="anim text-xxxl"></h1>
        <div class="cursor"></div>
      </div>
      <h2 class="text-xl">A 15-year old full-stack developer</h2>
      <div class="skills">
        <div class="skill-row">
          <Skill path="/python.svg" name="Python" class="skill" />
          <Skill path="/js.svg" name="JavaScript" class="skill" />
          <Skill path="/ts.svg" name="TypeScript" class="skill" />
          <Skill path="/kotlin.svg" name="Kotlin" class="skill" />
        </div>
      </div>
    </div>
    <div class="seal">
      <img src="/seal.png" alt="cute seal" class="seal-img" :class="{'spin': isSpinning}" id="seal" @mouseover="spin">
    </div>
  </div>
</section>
</template>

<style scoped>
.hero {
  display: grid;
  grid-template-columns: 65% 35%;
  width: 100%
}

.anim:after {
  content: "";
  animation: typewriter 1s linear 1;
  animation-fill-mode: forwards;
}

.cursor {
  display: block;
  background-color: white;
  height: 80px;
  width: 6px;
  margin-left: 5px;
  align-self: center;
  animation: 3s blink 0.85s linear infinite;
}

.hero h2 {
  color: #a1a1a1;
}


.title {
  height: 80vh;
  padding-left: 100px;
  align-content: center;
}

.skills {
  margin-top: 30px;
}

.skill-row {
  display: flex;
  margin-bottom: 20px;
}

.skill {
  margin-right: 25px
}

.seal {
  display: flex;
  align-items: center;
  justify-content: center;
}

.seal-img {
  height: 50vh;
  width: 50vh;
  border-radius: 100%;
}

.spin {
  animation: spin 2s ease;
}

@keyframes spin {
  from {
    transform: rotate(0deg);
  }
  to {
    transform: rotate(360deg);
  }
}

@keyframes blink {
  0% {
    opacity: 0;
  }
  50% {
    opacity: 100%;
  }
  100% {
    opacity: 0;
  }
}

@keyframes typewriter {
  0% {
    content: "I";
  }
  4% {
    content: "I'";
  }
  12% {
    content: "I'm";
  }
  22% {
    content: "I'm ";
  }
  29% {
    content: "I'm m";
  }
  34% {
    content: "I'm mv";
  }
  43% {
    content: "I'm mvl";
  }
  50% {
    content: "I'm mvlw";
  }
  57% {
    content: "I'm mvlwa";
  }
  65% {
    content: "I'm mvlwar";
  }
  71% {
    content: "I'm mvlware";
  }
  100% {
    content: "I'm mvlware";
  }
}

@media screen and (max-width: 768px) {
  .hero {
    display: flex;
    flex-direction: column;
  }

  .title {
    padding: 0 40px;
  }

  .title .text-xxxl {
    font-size: 2.8rem;
    text-align: center;
  }

  .title .text-xl {
    font-size: 2rem;
    text-align: center;
  }

  .cursor {
    height: 40px;
    width: 3px;
  }

  .skill-row {
    flex-direction: column;
    align-items: center;
  }

  .skill {
    margin: 10px 0;
  }

  .seal {
    display: block;
    align-self: center;
    margin-bottom: 30px;
  }

  .seal-img {
    margin: 0;
    height: 40vh;
    width: 40vh;
  }
}

</style>