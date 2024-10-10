<script setup lang="ts">
import { useRoute } from "vue-router";
import ProjectDetails from "@/components/ProjectDetails.vue";

const route = useRoute()
const id: string = route.params.id.toString()


</script>

<template>
<ProjectDetails :id="id" />
</template>

<style scoped>

</style>