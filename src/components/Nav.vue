<script setup lang="ts">
import IconMenu from "./icons/IconMenu.vue";
import IconClose from "./icons/IconClose.vue";
import { ref } from "vue";
const active = ref(false);
const toggle = () => (active.value = !active.value);
</script>
<template>
  <nav class="md:block fixed hidden w-full h-16 bg-black/75 z-50">
    <ul>
      <li><a href="#home">Home</a></li>
      <li><a href="#projects">Projects</a></li>
      <li><a href="#skills">Skills</a></li>
    </ul>
  </nav>
  <Transition name="fade">
    <div
      v-if="active"
      @click="toggle"
      class="fixed w-full h-full bg-black/75 md:hidden z-50"
    ></div>
  </Transition>
  <Transition name="slide">
    <nav
      v-if="active"
      class="fixed w-96 right-0 h-full bg-neutral-800 md:hidden z-50"
    >
      <ul>
        <li><a @click="toggle" href="#home">Home</a></li>
        <li><a @click="toggle" href="#projects">Projects</a></li>
        <li><a @click="toggle" href="#skills">Skills</a></li>
      </ul>
    </nav>
  </Transition>

  <button
    @click="toggle"
    class="fixed top-4 right-4 md:hidden flex justify-center items-center w-12 h-12 bg-neutral-700 rounded-full z-50"
  >
    <IconClose v-if="active" />
    <IconMenu v-else />
  </button>
</template>

<style scoped>
ul {
  @apply flex justify-center items-center flex-col md:flex-row gap-4 h-full;
}

a {
  @apply block text-lg p-4 text-neutral-400 hover:text-white;
}

.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.5s ease;
}

.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}

.slide-enter-active,
.slide-leave-active {
  transition: transform 0.1s ease;
}

.slide-enter-from,
.slide-leave-to {
  transform: translateX(100%);
}
</style>
