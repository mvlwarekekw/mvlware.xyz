<script setup lang="ts">

</script>

<template>
  <div class="wrapper">
    <div class="gradient-bar"></div>
  </div>
</template>

<style scoped>
.wrapper {
  display: flex;
  justify-content: center;
}

.gradient-bar {
  position: fixed;
  bottom: 10px;
  width: 97vw;
  height: 3px;
  background: linear-gradient(to bottom right, #ff00f2, #7700ff, #5300ff);
  border-radius: 30px;
}
</style>