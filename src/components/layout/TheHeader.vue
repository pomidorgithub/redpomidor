<template>
  <header class="fixed top-0 left-0 right-0 h-[72px] z-50 transition-all duration-300">
    <div
      class="bg-white dark:bg-black h-full transition-all duration-300"
      :class="{ 'bg-transparent': isScrolled }"
    >
      <div class="w-full h-full px-8">
        <div class="flex items-center justify-between h-full">
          <div class="flex items-center gap-8">
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

            <!-- Navigation links -->
            <nav class="flex gap-8">
              <RouterLink
                to="/cases"
                class="text-sm tracking-[0.2em] link-hover"
                :class="{ 'text-black': !isDark, 'text-white': isDark }"
                >КЕЙСЫ</RouterLink
              >
              <RouterLink
                to="/services"
                class="text-sm tracking-[0.2em] link-hover"
                :class="{ 'text-black': !isDark, 'text-white': isDark }"
                >УСЛУГИ</RouterLink
              >
            </nav>
          </div>

          <!-- Logo -->
          <RouterLink
            to="/"
            class="absolute left-1/2 top-1/2 -translate-x-1/2 -translate-y-1/2 transition-all duration-300"
            :class="{ 'scale-125': isScrolled }"
          >
            <LogoIcon class="w-8 h-8" />
          </RouterLink>

          <!-- Theme toggle -->
          <button @click="toggleTheme" class="transition-transform duration-300 hover:scale-110">
            <SunIcon v-if="isDark" class="w-6 h-6" />
            <MoonIcon v-else class="w-6 h-6" />
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
import SunIcon from '../icons/SunIcon.vue'
import MoonIcon from '../icons/MoonIcon.vue'

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
  @apply relative;
}

.link-hover::after {
  @apply content-[''] absolute left-0 bottom-[-4px] w-0 h-[1px] bg-[#FF3B30] transition-all duration-300;
}

.link-hover:hover::after {
  @apply w-full;
}
</style>
