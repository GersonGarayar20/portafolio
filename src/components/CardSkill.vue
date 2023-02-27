<script setup lang="ts">
const { name, image } = defineProps(["name", "image"]);
</script>
<template>
  <div class="p-5 flex items-center gap-4 bg-neutral-800 rounded">
    <img class="w-10 h-10" :src="image" :alt="name" />
    <p class="text-neutral-300">{{ name }}</p>
  </div>
</template>

<style scoped></style>
