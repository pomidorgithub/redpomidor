<template>
  <!-- 
    Root container
    - min-h-screen: занимает всю высоту экрана
    - flex flex-col: вертикальное расположение элементов
    - bg и text классы для темной темы
  -->
  <div class="min-h-screen flex flex-col bg-white dark:bg-black text-black dark:text-white transition-colors duration-300">
    <!-- 
      Header section
      - fixed: фиксированное положение
      - h-[72px]: фиксированная высота
      - z-50: всегда поверх контента
    -->
    <TheHeader @toggle-sidebar="$emit('toggle-sidebar')" />
    
    <!-- 
      Main content section
      - pt-[72px]: отступ под фиксированный header
      - flex-1: занимает все доступное пространство
      - w-full: растягивается на всю ширину
    -->
    <main class="flex-1 pt-[72px] w-full">
      <!-- Сюда вставляется содержимое страницы -->
      <slot />
    </main>

    <!-- 
      Footer section
      - mt-auto: прижимается к низу при недостатке контента
      - w-full: растягивается на всю ширину
    -->
    <TheFooter />
  </div>
</template>

<script setup>
import TheHeader from './TheHeader.vue'
import TheFooter from './TheFooter.vue'

defineEmits(['toggle-sidebar'])
</script>

<style>
/* 
  Глобальные стили
  - Определяем переменные
  - Базовые стили для текста
  - Утилиты для повторяющихся элементов
*/
:root {
  /* Размеры */
  --header-height: 72px;
  --container-padding: 2rem;
  
  /* Шрифты */
  --font-sans: ui-sans-serif, system-ui, -apple-system, sans-serif;
}

/* Базовые стили */
body {
  font-family: var(--font-sans);
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

/* Утилиты */
.link-hover {
  @apply hover:text-neutral-500 dark:hover:text-neutral-400 transition-colors duration-300;
}
</style>
