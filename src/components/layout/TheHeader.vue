<template>
  <header class="fixed top-0 left-0 right-0 h-[72px] z-50 transition-all duration-300">
    <div
      class="bg-white dark:bg-black h-full transition-all duration-300"
      :class="{ 'bg-transparent': isScrolled }"
    >
      <div class="w-full h-full px-8">
        <div class="flex items-center justify-between h-full">
          <!-- Menu button -->
          <button
            @click="toggleSidebar"
            class="flex flex-col gap-2 text-sm tracking-[0.2em] transition-colors group"
          >
            <div
              class="w-6 h-[1px] bg-current transform transition-all duration-300"
              :class="{ 'h-[2px] bg-[#FF3B30]': isScrolled }"
            ></div>
            <div
              class="w-6 h-[1px] bg-current transform transition-all duration-300"
              :class="{ 'h-[2px] bg-[#FF3B30]': isScrolled }"
            ></div>
          </button>

          <!-- Logo -->
          <RouterLink
            to="/"
            class="absolute left-1/2 top-1/2 -translate-x-1/2 -translate-y-1/2 transition-all duration-300"
            :class="{ 'scale-125': isScrolled }"
          >
            <LogoIcon class="w-8 h-8" />
          </RouterLink>

          <!-- Theme toggle -->
          <button @click="toggleTheme" class="text-sm tracking-[0.2em] transition-colors">
            {{ isDark ? 'LIGHT' : 'DARK' }}
          </button>
        </div>
      </div>
    </div>
  </header>
</template>

<script setup>
import { ref, onMounted, onUnmounted, computed } from 'vue'
import { useThemeStore } from '../../stores/theme'
import LogoIcon from '../icons/LogoIcon.vue'

const themeStore = useThemeStore()
const isDark = computed(() => themeStore.isDark)
const isScrolled = ref(false)

const checkScroll = () => {
  isScrolled.value = window.scrollY > 0
}

onMounted(() => {
  window.addEventListener('scroll', checkScroll)
})

onUnmounted(() => {
  window.removeEventListener('scroll', checkScroll)
})

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
