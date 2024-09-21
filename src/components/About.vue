<script setup lang="ts">

</script>

<template>
<section>
  <div class="about">
    <div class="aboutme">
      <h2 class="text-xl">// About Me</h2>
      <p class="text-md">Hey there! I'm Andrin, a 15-year-old high school student from Zurich. When I'm not in school, you'll probably find me gaming or doing coding projects.  I love seals</p>
    </div>
    <div class="seal">
      <img src="/src/assets/seal.png" alt="cute seal" class="seal-img" id="seal">
    </div>
  </div>
</section>
</template>

<style scoped>
.about {
  display: grid;
  grid-template-columns: 65% 35%;
  width: 100%;
}

.aboutme {
  display: flex;
  flex-direction: column;
  justify-content: center;
  height: 80vh;
  padding-left: 100px;
}

.aboutme p {
  max-width: 40vw;
}

.seal {
  display: flex;
  height: 80vh;
  align-items: center;
  justify-content: center;
}

.seal-img {
  height: 50vh;
  width: 50vh;
  border-radius: 100%;
}
</style>