<script setup lang="ts">
import { defineProps } from 'vue'
import Skill from "@/components/Skill.vue";

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
<div class="border">
  <Skill v-bind:name="name" v-bind:path="path" class="skill" />
</div>
</template>

<style scoped>
.border {
  border: 1px solid white;
  padding: 3px 5px;
  border-radius: 8px;
  opacity: 50%;
}

@media screen and (max-width: 768px) {
  .border {
    margin-top: 10px;
  }
}

</style>