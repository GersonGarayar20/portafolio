<script setup lang="ts">
import { projects } from "./projects";
import CardProject from "./CardProject.vue";
</script>
<template>
  <section class="grid gap-8 lg:grid-cols-3 md:grid-cols-2">
    <CardProject
      v-for="({ title, url, github, img, tags }, i) in projects"
      :key="i"
      :title="title"
      :url="url"
      :github="github"
      :img="img"
      :tags="tags"
    />
  </section>
</template>

<style scoped></style>
