<template>
  <!--
    Root container
    - min-h-screen: занимает всю высоту экрана
    - flex flex-col: вертикальное расположение элементов
    - bg и text классы для темной темы
  -->
  <div class="app-layout">
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
    <main class="main-content">
      <!-- Сюда вставляется содержимое страницы -->
      <slot />
    </main>

    <!--
      Footer section
      - mt-auto: прижимается к низу при недостатке контента
      - w-full: растягивается на всю ширину
    -->
    <TheFooter />

    <!-- Cookie Consent -->
    <CookieConsent />
  </div>
</template>

<script setup>
import TheHeader from './TheHeader.vue'
import TheFooter from './TheFooter.vue'
import CookieConsent from '../common/CookieConsent.vue'

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

<style scoped>
.app-layout {
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  background: var(--color-bg-primary);
  color: var(--color-text-primary);
  transition:
    background-color var(--transition-normal),
    color var(--transition-normal);
}

.main-content {
  flex: 1;
  width: 100%;
}

/* Обеспечиваем правильную работу с фиксированным хедером */
@media (min-width: 1024px) {
  .main-content {
    padding-top: 0;
  }
}
</style>
