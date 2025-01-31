<template>
  <header class="fixed top-0 left-0 right-0 h-[72px] bg-white dark:bg-black z-50 w-full">
    <div class="w-full h-full px-8">
      <div class="flex items-center justify-between h-full">
        <!-- Menu button -->
        <button 
          class="text-sm tracking-[0.2em] font-light link-hover"
          @click="toggleSidebar"
        >
          [ MENU ]
        </button>

        <!-- Logo -->
        <div class="absolute left-1/2 top-1/2 -translate-x-1/2 -translate-y-1/2">
          <LogoIcon class="w-6 h-6" />
        </div>

        <!-- Theme toggle -->
        <button 
          class="text-sm tracking-[0.2em] font-light link-hover"
          @click="toggleTheme"
        >
          [ {{ isDark ? 'LIGHT' : 'DARK' }} ]
        </button>
      </div>
    </div>
  </header>
</template>

<script setup>
import { computed } from 'vue'
import { useThemeStore } from '../../stores/theme'
import LogoIcon from '../icons/LogoIcon.vue'

const themeStore = useThemeStore()
const isDark = computed(() => themeStore.isDark)

const toggleTheme = () => {
  themeStore.toggleTheme()
}

const toggleSidebar = () => {
  emit('toggle-sidebar')
}

const emit = defineEmits(['toggle-sidebar'])
</script>

<style scoped>
.link-hover {
  @apply hover:text-neutral-500 dark:hover:text-neutral-400 transition-colors duration-300;
}
</style>
