<script setup lang="ts">
import IconGitHub from "./icons/IconGitHub.vue";
const { title, url, github, img, tags } = defineProps([
  "title",
  "url",
  "github",
  "img",
  "tags",
]);
</script>
<template>
  <figure>
    <a :href="url" target="_blank" rel="noopener noreferrer">
      <img
        class="hover:brightness-75 rounded-xl transition-all"
        :src="img"
        :alt="title"
      />
    </a>

    <figcaption class="flex justify-between pt-4 pb-2">
      <a
        class="block text-xl hover:text-neutral-200 text-neutral-400 transition-all hover:underline"
        :href="url"
        title="Ver proyecto"
        target="_blank"
        rel="noopener noreferrer"
      >
        {{ title }}
      </a>
      <a
        class="fill-neutral-400 hover:fill-neutral-200"
        :href="github"
        title="Ver codigo"
        target="_blank"
        rel="noopener noreferrer"
      >
        <IconGitHub />
      </a>
    </figcaption>
    <div class="flex gap-2 pb-4">
      <img
        class="w-6"
        v-for="tag in tags"
        :title="tag"
        :src="`svg/${tag}.svg`"
        alt=""
      />
    </div>
  </figure>
</template>

<style scoped></style>
