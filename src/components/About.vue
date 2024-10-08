<script setup lang="ts">

</script>

<template>
<section>
  <div class="about">
    <div class="aboutme">
      <h2 class="text-xl">// About Me</h2>
      <p class="text-md">Hey there! I'm Andrin, a 15-year-old high school student from Zurich. When I'm not in school, you'll probably find me gaming or doing coding projects.  I love seals</p>
      <br>
      <div>
        <a href="/projects" class="projects-link">
          <img class="arrow" src="/arrow.svg" alt="">
          <h3 class="text-md">Projects</h3>
        </a>
      </div>
      <div class="wrapper dc">
        <img src="/discord-light.svg" alt="" class="discord">
        <p class="text-md">@mvlware</p>
      </div>
      <div class="wrapper">
        <img src="/email.svg" alt="" class="email">
        <p class="text-md">mal@mvlware.xyz</p>
      </div>
    </div>
    <div class="seal">
      <img src="/seal.png" alt="cute seal" class="seal-img" id="seal">
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

.aboutme h2 {
  margin-bottom: 50px;
}

.aboutme p {
  max-width: 40vw;
}

.wrapper {
  display: flex;
  align-items: center;
}

.projects-link {
  display: flex;
  justify-items: center;
  align-items: center;
}

.projects-link h3 {
  margin-left: 10px;
}

.arrow{
  height: 30px;
}


.dc {
  margin: 30px 0;
}

.discord {
  width: 42px;
  height: 42px;
  margin-right: 30px;
  margin-left: 5px;
  padding: 0;
}

.email {
  width: 42px;
  height: 42px;
  margin-right: 20px;
  zoom: 120%;
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

@media screen and (max-width: 768px) {
  .about {
    display: flex;
    flex-direction: column;
    justify-content: center;
  }

  .aboutme {
    height: 100%;
    padding: 20px 40px;
  }

  .aboutme p {
    max-width: 75vw;
  }

  .seal {
    height: 50vh;
  }

  .seal-img {
    height: 40vh;
    width: 40vh;
  }
}

</style>