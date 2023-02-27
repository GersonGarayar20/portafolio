<script setup lang="ts">
import { ref } from "vue";
import CardSkill from "./CardSkill.vue";
import { backend, frontend } from "./skills";
const select = ref("front");
</script>
<template>
  <section class="">
    <ul class="flex justify-center md:justify-start mb-8">
      <li
        :class="select === 'front' ? 'border-b-2' : ''"
        class="border-teal-400"
      >
        <button
          @click="select = 'front'"
          class="text-neutral-400 hover:text-neutral-300 px-4 py-2"
        >
          Frontend
        </button>
      </li>
      <li
        :class="select === 'back' ? 'border-b-2' : ''"
        class="border-teal-400"
      >
        <button
          @click="select = 'back'"
          class="text-neutral-400 hover:text-neutral-300 px-4 py-2"
        >
          Backend
        </button>
      </li>
    </ul>
    <div
      class="grid sm:grid-cols-2 md:grid-cols-3 lg:grid-cols-4 xl:grid-cols-5 gap-3"
    >
      <CardSkill
        v-if="select === 'front'"
        v-for="({ name, image }, i) in frontend"
        :key="i"
        :name="name"
        :image="image"
      />
      <CardSkill
        v-if="select === 'back'"
        v-for="({ name, image }, i) in backend"
        :key="i"
        :name="name"
        :image="image"
      />
    </div>
  </section>
</template>

<style scoped></style>
