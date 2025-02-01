<template>
  <section class="min-h-[calc(100vh-72px)] bg-neutral-50 dark:bg-neutral-950">
    <div class="h-full w-full">
      <!-- Основной контент -->
      <div class="px-8 pt-32">
        <div class="max-w-[120rem] mx-auto">
          <!-- Заголовок -->
          <div class="space-y-16"
            v-motion
            :initial="{ opacity: 0 }"
            :enter="{ opacity: 1 }"
          >
            <div class="relative">
              <h1 class="text-[43px] leading-[0.9] tracking-[-0.02em]">
                СОЗДАЁМ<br />
                ЦИФРОВЫЕ<br />
                ПРОДУКТЫ
              </h1>
            </div>
            
            <div class="grid grid-cols-1 md:grid-cols-2 gap-16">
              <div class="text-lg md:text-xl text-neutral-600 dark:text-neutral-300">
                Мы разрабатываем современные веб-сайты и приложения, которые помогают бизнесу расти в цифровом пространстве.
              </div>
            </div>
          </div>

          <!-- Статистика и кнопка -->
          <div class="mt-24 flex flex-col md:flex-row md:justify-between md:items-end gap-16"
            v-motion
            :initial="{ opacity: 0, y: 40 }"
            :enter="{ opacity: 1, y: 0 }"
            :delay="200"
          >
            <div class="grid grid-cols-1 sm:grid-cols-3 gap-12 md:gap-24">
              <div>
                <div class="text-4xl md:text-5xl mb-3">50+</div>
                <div class="text-sm tracking-[0.2em] text-neutral-500">ПРОЕКТОВ</div>
              </div>
              <div>
                <div class="text-4xl md:text-5xl mb-3">98%</div>
                <div class="text-sm tracking-[0.2em] text-neutral-500">КЛИЕНТОВ</div>
              </div>
              <div>
                <div class="text-4xl md:text-5xl mb-3">15+</div>
                <div class="text-sm tracking-[0.2em] text-neutral-500">ЛЕТ</div>
              </div>
            </div>

            <button
              @click="scrollToProjects"
              class="group relative inline-flex items-center gap-6 text-sm tracking-[0.2em] hover:text-neutral-500 transition-colors"
            >
              <span class="relative z-10">СМОТРЕТЬ РАБОТЫ</span>
              <div class="relative w-10 h-10 rounded-full border border-current group-hover:bg-black group-hover:border-black dark:group-hover:bg-white dark:group-hover:border-white transition-colors">
                <svg 
                  class="absolute inset-0 m-auto w-5 h-5 group-hover:text-white dark:group-hover:text-black transition-colors"
                  viewBox="0 0 24 24"
                  fill="none"
                  stroke="currentColor"
                  stroke-width="1.5"
                >
                  <path d="M17 7L7 17M17 7H7M17 7V17" />
                </svg>
              </div>
            </button>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
const scrollToProjects = () => {
  const projectsSection = document.getElementById('projects')
  if (projectsSection) {
    projectsSection.scrollIntoView({ behavior: 'smooth' })
  }
}
</script>
