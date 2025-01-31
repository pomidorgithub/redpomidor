<template>
  <section class="min-h-[calc(100vh-72px)] flex items-center justify-center w-full" :class="{ 'is-dark': isDark }">
    <div class="w-full px-8 relative z-10">
      <div class="max-w-[90rem] mx-auto">
        <h1 class="text-center">
          <div class="space-y-2">
            <div class="text-sm tracking-[0.2em] text-neutral-500 dark:text-neutral-400 mb-8">
              [ КРЕАТИВНОСТЬ × ПЕРФЕКЦИОНИЗМ ]
            </div>
            <div class="text-[5rem] md:text-[8rem] xl:text-[12rem] font-light leading-[0.9] tracking-tight">
              WILD
            </div>
            <div class="text-[5rem] md:text-[8rem] xl:text-[12rem] font-light leading-[0.9] tracking-tight text-primary dark:text-primary-light">
              INTEREST
            </div>
            <div class="text-base md:text-lg tracking-[0.2em] text-neutral-500 dark:text-neutral-400 mt-8">
              [ ДИКИЙ ИНТЕРЕС К ДЕЛУ ]
            </div>
          </div>
        </h1>
      </div>
    </div>
  </section>
</template>

<script setup>
import { computed } from 'vue'
import { useThemeStore } from '../../stores/theme'

const themeStore = useThemeStore()
const isDark = computed(() => themeStore.isDark)
</script>

<style scoped>
.hero-section {
  @apply bg-white transition-colors duration-700;
}

.hero-section.is-dark {
  @apply bg-black;
}
</style>

<style>
/* Определяем цвета для светлой темы */
:root {
  --tw-color-primary: #FF3B30;
  --tw-color-primary-light: #FF4D42;
}

/* Определяем цвета для темной темы */
.dark {
  --tw-color-primary: #FF4D42;
  --tw-color-primary-light: #FF5E54;
}

/* Утилиты для цветов */
.text-primary {
  color: var(--tw-color-primary);
}

.text-primary-light {
  color: var(--tw-color-primary-light);
}

.bg-primary {
  background-color: var(--tw-color-primary);
}

.dark .text-primary-light {
  color: var(--tw-color-primary-light);
}

.dark .bg-primary {
  background-color: var(--tw-color-primary);
}
</style>
