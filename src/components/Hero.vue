<script setup lang="ts">
import {ref} from "vue";

const isSpinning = ref(false)

const spin = () => {
  isSpinning.value = !isSpinning.value
}
</script>

<template>
<section>
  <div class="hero">
    <div class="title">
      <h1 class="text-xxxl">Heya,<br>I'm mvlware</h1>
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

.title {
  height: 80vh;
  padding-left: 100px;
  align-content: center;
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

.spin {
  animation:spin 2s ease;
}

@keyframes spin {
  from {
    transform: rotate(0deg);
  }
  to {
    transform: rotate(360deg);
  }
}

</style>