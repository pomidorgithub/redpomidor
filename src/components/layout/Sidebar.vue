<script setup>
import { computed } from 'vue'
import { useThemeStore } from '../../stores/theme'
import LogoIcon from '../icons/LogoIcon.vue'
import SunIcon from '../icons/SunIcon.vue'
import MoonIcon from '../icons/MoonIcon.vue'
const links = [
  { to: '/cases', text: 'КЕЙСЫ' },
  { to: '/services', text: 'УСЛУГИ' },
  { to: '/about', text: 'О НАС' },
  { to: '/contact', text: 'КОНТАКТЫ' },
]
const props = defineProps({
  isOpen: {
    type: Boolean,
    required: true,
  },
})

defineEmits(['close'])

const themeStore = useThemeStore()
const isDark = computed(() => themeStore.isDark)
const toggleTheme = () => themeStore.toggleTheme()
</script>

<template>
  <div
    class="fixed inset-0 transform transition-all duration-500 z-[100]"
    :class="[isDark ? 'bg-black/95' : 'bg-white/95', isOpen ? 'translate-x-0' : 'translate-x-full']"
  >
    <!-- Header с кнопкой закрытия -->
    <div class="h-[72px] backdrop-blur-sm">
      <div class="w-full h-full px-8">
        <div class="flex items-center justify-between h-full relative">
          <!-- Кнопка закрытия (на месте бургера) -->
          <button
            @click="$emit('close')"
            class="flex flex-col gap-2 text-sm tracking-[0.2em] transition-all duration-300 group"
          >
            <div class="relative w-6 h-6">
              <div
                class="absolute top-1/2 left-0 w-6 h-[2px] transition-all duration-300 group-hover:w-8"
                :class="[isDark ? 'bg-white' : 'bg-black', 'rotate-45 group-hover:bg-[#FF3B30]']"
              ></div>
              <div
                class="absolute top-1/2 left-0 w-6 h-[2px] transition-all duration-300 group-hover:w-8"
                :class="[isDark ? 'bg-white' : 'bg-black', '-rotate-45 group-hover:bg-[#FF3B30]']"
              ></div>
            </div>
          </button>

          <!-- Логотип -->
          <RouterLink
            to="/"
            class="absolute left-1/2 top-1/2 -translate-x-1/2 -translate-y-1/2 transition-all duration-300 hover:scale-110"
            @click="$emit('close')"
          >
            <LogoIcon class="w-8 h-8" />
          </RouterLink>

          <!-- Переключатель темы -->
          <button
            @click="toggleTheme"
            class="transition-all duration-300 hover:scale-110 hover:rotate-90"
          >
            <SunIcon v-if="isDark" class="w-6 h-6" />
            <MoonIcon v-else class="w-6 h-6" />
          </button>
        </div>
      </div>
    </div>

    <!-- Навигация -->
    <div
      class="flex flex-col h-[calc(100vh-80px)] justify-center items-center w-full max-w-2xl mx-auto px-8"
    >
      <nav class="flex flex-col gap-12 text-center w-full">
        <RouterLink
          v-for="(link, index) in links"
          :key="index"
          :to="link.to"
          class="text-5xl font-light tracking-wider transition-all duration-300 relative menu-link opacity-0 w-full"
          :class="[
            isDark ? 'text-white' : 'text-black',
            isOpen ? 'translate-y-0 opacity-100' : 'translate-y-8 opacity-0',
            `delay-[${index * 100}ms]`,
          ]"
          @click="$emit('close')"
        >
          {{ link.text }}
        </RouterLink>
      </nav>
    </div>
  </div>
</template>

<style scoped>
.menu-link {
  @apply relative inline-block;
  width: fit-content !important;
  margin: 0 auto;
}

.menu-link::after {
  content: '';
  position: absolute;
  bottom: -8px;
  left: 50%;
  width: 0;
  height: 2px;
  background-color: #ff3b30;
  transition: all 0.3s ease-in-out;
  transform: translateX(-50%);
}

.menu-link:hover::after {
  width: 100%;
}

.menu-link:hover {
  transform: scale(1.05);
}

/* Анимация появления для ссылок */
@keyframes fadeInUp {
  from {
    opacity: 0;
    transform: translateY(20px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

.menu-link {
  animation: fadeInUp 0.5s ease-out forwards;
}
</style>
