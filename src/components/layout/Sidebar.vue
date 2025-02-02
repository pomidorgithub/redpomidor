<script setup>
import { computed } from 'vue'
import { useThemeStore } from '../../stores/theme'
import LogoIcon from '../icons/LogoIcon.vue'
import SunIcon from '../icons/SunIcon.vue'
import MoonIcon from '../icons/MoonIcon.vue'

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
    class="fixed inset-0 transform transition-transform duration-300 z-[100]"
    :class="[isDark ? 'bg-black' : 'bg-white', isOpen ? 'translate-x-0' : 'translate-x-full']"
  >
    <!-- Header с кнопкой закрытия -->
    <div class="h-[72px]">
      <div class="w-full h-full px-8">
        <div class="flex items-center justify-between h-full relative">
          <!-- Кнопка закрытия (на месте бургера) -->
          <button
            @click="$emit('close')"
            class="flex flex-col gap-2 text-sm tracking-[0.2em] transition-colors group"
          >
            <div class="relative w-6 h-6">
              <div
                class="absolute top-1/2 left-0 w-6 h-[1px] transition-all rotate-45 group-hover:bg-[#FF3B30]"
                :class="isDark ? 'bg-white' : 'bg-black'"
              ></div>
              <div
                class="absolute top-1/2 left-0 w-6 h-[1px] transition-all -rotate-45 group-hover:bg-[#FF3B30]"
                :class="isDark ? 'bg-white' : 'bg-black'"
              ></div>
            </div>
          </button>

          <!-- Логотип (центрирован как в хедере) -->
          <RouterLink
            to="/"
            class="absolute left-1/2 top-1/2 -translate-x-1/2 -translate-y-1/2"
            @click="$emit('close')"
          >
            <LogoIcon class="w-8 h-8" />
          </RouterLink>

          <!-- Переключатель темы -->
          <button @click="toggleTheme" class="transition-transform duration-300 hover:scale-110">
            <SunIcon v-if="isDark" class="w-6 h-6" />
            <MoonIcon v-else class="w-6 h-6" />
          </button>
        </div>
      </div>
    </div>

    <!-- Навигация -->
    <div class="flex flex-col h-[calc(100vh-80px)] justify-center items-center">
      <nav class="flex flex-col gap-8 text-[60px] font-light text-center">
        <RouterLink
          to="/"
          class="transition-colors duration-300"
          :class="isDark ? 'text-white hover:text-zinc-300' : 'text-black hover:text-zinc-600'"
          @click="$emit('close')"
        >
          HOME
        </RouterLink>
        <RouterLink
          to="/cases"
          class="text-5xl font-light tracking-wider transition-colors hover:text-[#FF3B30]"
          :class="isDark ? 'text-white' : 'text-black'"
          @click="$emit('close')"
        >
          КЕЙСЫ
        </RouterLink>
        <RouterLink
          to="/services"
          class="text-5xl font-light tracking-wider transition-colors hover:text-[#FF3B30]"
          :class="isDark ? 'text-white' : 'text-black'"
          @click="$emit('close')"
        >
          УСЛУГИ
        </RouterLink>
        <RouterLink
          to="/about"
          class="text-5xl font-light tracking-wider transition-colors hover:text-[#FF3B30]"
          :class="isDark ? 'text-white' : 'text-black'"
          @click="$emit('close')"
        >
          О НАС
        </RouterLink>
        <RouterLink
          to="/contact"
          class="text-5xl font-light tracking-wider transition-colors hover:text-[#FF3B30]"
          :class="isDark ? 'text-white' : 'text-black'"
          @click="$emit('close')"
        >
          КОНТАКТЫ
        </RouterLink>
      </nav>
    </div>
  </div>
</template>
