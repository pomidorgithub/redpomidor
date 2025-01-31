<template>
  <div
    class="fixed inset-0 bg-black transform transition-transform duration-500 origin-top z-[100]"
    :class="{ 'scale-y-0': !isOpen }"
  >
    <!-- Header с кнопкой закрытия -->
    <div class="py-3 px-4">
      <div class="flex justify-between items-center max-w-7xl mx-auto">
        <div class="flex items-center gap-2">
          <LogoIcon class="w-6 h-6" />
          <span class="text-sm tracking-[0.2em] text-white">REDPOMIDOR</span>
        </div>
        <div class="flex items-center gap-6">
          <button
            class="text-sm tracking-[0.2em] text-white hover:text-zinc-300 transition-colors duration-300"
            @click="toggleTheme"
          >
            {{ isDark ? 'LIGHT' : 'DARK' }}
          </button>
          <button
            @click="$emit('close')"
            class="flex flex-col gap-2 text-sm tracking-[0.2em] hover:text-[#FF3B30] transition-colors"
          >
            <div class="w-6 h-[1px] bg-current"></div>
            <div class="w-6 h-[1px] bg-current"></div>
          </button>
        </div>
      </div>
    </div>

    <!-- Навигация -->
    <div class="flex flex-col h-[calc(100vh-80px)] justify-center items-center">
      <nav class="flex flex-col gap-8 text-[60px] font-light text-white text-center">
        <router-link
          to="/"
          class="hover:text-zinc-300 transition-colors duration-300"
          @click="$emit('close')"
        >
          HOME
        </router-link>
        <router-link
          to="/cases"
          class="text-5xl font-light tracking-wider hover:text-[#FF3B30] transition-colors"
          @click="$emit('close')"
        >
          КЕЙСЫ
        </router-link>
        <router-link
          to="/services"
          class="text-5xl font-light tracking-wider hover:text-[#FF3B30] transition-colors"
          @click="$emit('close')"
        >
          УСЛУГИ
        </router-link>
        <router-link
          to="/about"
          class="text-5xl font-light tracking-wider hover:text-[#FF3B30] transition-colors"
          @click="$emit('close')"
        >
          О НАС
        </router-link>
        <router-link
          to="/contact"
          class="text-5xl font-light tracking-wider hover:text-[#FF3B30] transition-colors"
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
  @apply text-zinc-700;
}
</style>
