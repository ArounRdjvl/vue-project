<script setup lang="ts">
import { useDark } from '@vueuse/core'

const isDark = useDark()
</script>

<template>
  <footer
    class="relative md:absolute inset-x-0 bottom-0 m-2 h-16 flex justify-end gap-1 items-center"
  >
    <a href="https://github.com/ArounRdjvl/vue-project">
      <img
        v-if="isDark"
        src="@/assets/github-mark-white.svg"
        class="object-cover h-6 right-1 m-2"
      />
      <img v-else src="@/assets/github-mark.svg" class="object-cover h-6 right-1 m-2" />
    </a>
    <a href="https://www.linkedin.com/in/aroun-radjavelou/">
      <img src="@/assets/linkedIn.png" class="object-cover h-6 right-1 m-2" />
    </a>
  </footer>
</template>
