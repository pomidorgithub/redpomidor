<template>
  <div
    class="fixed inset-0 transform transition-transform duration-500 origin-top z-[100]"
    :class="[
      isDark ? 'bg-black' : 'bg-white',
      { 'scale-y-0': !isOpen }
    ]"
  >
    <!-- Header с кнопкой закрытия -->
    <div class="py-3 px-4">
      <div class="flex justify-between items-center max-w-7xl mx-auto">
        <div class="flex items-center gap-2">
          <LogoIcon class="w-6 h-6" />
          <span class="text-sm tracking-[0.2em]" :class="isDark ? 'text-white' : 'text-black'">REDPOMIDOR</span>
        </div>
        <div class="flex items-center gap-6">
          <button
            class="text-sm tracking-[0.2em] transition-colors duration-300"
            :class="isDark ? 'text-white hover:text-zinc-300' : 'text-black hover:text-zinc-600'"
            @click="toggleTheme"
          >
            {{ isDark ? 'LIGHT' : 'DARK' }}
          </button>
          <button
            @click="$emit('close')"
            class="w-12 h-12 flex items-center justify-center group"
          >
            <div class="relative w-6 h-6">
              <div class="absolute top-1/2 left-0 w-6 h-[1px] transition-all rotate-45 group-hover:bg-[#FF3B30]"
                   :class="isDark ? 'bg-white' : 'bg-black'"></div>
              <div class="absolute top-1/2 left-0 w-6 h-[1px] transition-all -rotate-45 group-hover:bg-[#FF3B30]"
                   :class="isDark ? 'bg-white' : 'bg-black'"></div>
            </div>
          </button>
        </div>
      </div>
    </div>

    <!-- Навигация -->
    <div class="flex flex-col h-[calc(100vh-80px)] justify-center items-center">
      <nav class="flex flex-col gap-8 text-[60px] font-light text-center">
        <router-link
          to="/"
          class="transition-colors duration-300"
          :class="isDark ? 'text-white hover:text-zinc-300' : 'text-black hover:text-zinc-600'"
          @click="$emit('close')"
        >
          HOME
        </router-link>
        <router-link
          to="/cases"
          class="text-5xl font-light tracking-wider transition-colors hover:text-[#FF3B30]"
          :class="isDark ? 'text-white' : 'text-black'"
          @click="$emit('close')"
        >
          КЕЙСЫ
        </router-link>
        <router-link
          to="/services"
          class="text-5xl font-light tracking-wider transition-colors hover:text-[#FF3B30]"
          :class="isDark ? 'text-white' : 'text-black'"
          @click="$emit('close')"
        >
          УСЛУГИ
        </router-link>
        <router-link
          to="/about"
          class="text-5xl font-light tracking-wider transition-colors hover:text-[#FF3B30]"
          :class="isDark ? 'text-white' : 'text-black'"
          @click="$emit('close')"
        >
          О НАС
        </router-link>
        <router-link
          to="/contact"
          class="text-5xl font-light tracking-wider transition-colors hover:text-[#FF3B30]"
          :class="isDark ? 'text-white' : 'text-black'"
          @click="$emit('close')"
        >
          КОНТАКТЫ
        </router-link>
      </nav>
    </div>
  </div>
</template>

<script setup>
import { computed } from 'vue'
import { useThemeStore } from '../../stores/theme'
import LogoIcon from '../icons/LogoIcon.vue'

defineProps({
  isOpen: {
    type: Boolean,
    required: true
  }
})

const themeStore = useThemeStore()
const isDark = computed(() => themeStore.isDark)
const toggleTheme = () => themeStore.toggleTheme()

defineEmits(['close'])
</script>

<style scoped>
.router-link-active {
  @apply text-zinc-700 dark:text-zinc-300;
}
</style>
