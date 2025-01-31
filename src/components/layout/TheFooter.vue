<template>
  <footer class="w-full bg-white dark:bg-black border-t border-neutral-200 dark:border-neutral-800">
    <div class="w-full px-8 py-8">
      <div class="flex flex-col md:flex-row justify-between items-center gap-4">
        <!-- Logo and copyright -->
        <div class="flex items-center gap-2">
          <LogoIcon class="w-6 h-6" />
          <span class="text-sm tracking-[0.2em]">REDPOMIDOR</span>
        </div>

        <!-- Links -->
        <nav class="flex items-center gap-8">
          <a href="#" class="text-sm tracking-[0.2em] link-hover">INSTAGRAM</a>
          <a href="#" class="text-sm tracking-[0.2em] link-hover">BEHANCE</a>
          <a href="#" class="text-sm tracking-[0.2em] link-hover">GITHUB</a>
        </nav>

        <!-- Copyright -->
        <div class="text-sm text-neutral-600 dark:text-neutral-400">
          {{ currentYear }} All rights reserved
        </div>
      </div>
    </div>
  </footer>
</template>

<script setup>
import LogoIcon from '../icons/LogoIcon.vue'
const currentYear = new Date().getFullYear()
</script>

<style scoped>
.link-hover {
  @apply hover:text-neutral-500 dark:hover:text-neutral-400 transition-colors duration-300;
}
</style>
