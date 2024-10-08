<script setup lang="ts">
defineProps({
  name: {
    type: String,
    default: "Python"
  },
  path: {
    type: String,
    default: "/python.svg"
  }
})
</script>

<template>
<div class="skill">
  <div class="skill-icon">
    <img :src="path" alt="" height="30px" width="30px">
  </div>
  <div class="skill-name">
    <h3 class="text-md">{{ name }}</h3>
  </div>
</div>
</template>

<style scoped>
.skill {
  display: flex;
  align-items: center;
  justify-items: center;
}

.skill-icon {
  display: flex;
  justify-content: center;
  margin-right: 12px;
}
</style>