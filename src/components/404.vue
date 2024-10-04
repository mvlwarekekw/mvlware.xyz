<script setup lang="ts">

</script>

<template>
<div class="wrapper">
  <h1 class="text-xxxl">404 Not Found</h1>
  <h2 class="text-xl">what exactly are you looking for?</h2>
  <img src="/confused_seal.png" alt="" class="seal">
</div>
</template>

<style scoped>
.wrapper {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  height: 80vh;
}

.seal {
  border-radius: 100%;
  height: 40vh;
  width: 40vh;
  margin: 50px 0;
}

@media screen and (max-width: 768px) {
  .wrapper {
    height: 100%;
    width: 90%;
    padding: 0 20px;
  }

  .wrapper .text-xxxl, .wrapper .text-xl {
    text-align: center;
    line-height: 120%;
  }
}
</style>