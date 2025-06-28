<template>
  <section class="min-h-[calc(100vh-72px)] bg-white dark:bg-black overflow-hidden">
    <div class="relative">
      <!-- Фоновая сетка -->
      <div class="absolute inset-0 grid grid-cols-2 md:grid-cols-4 opacity-30">
        <div class="border-r border-neutral-100 dark:border-neutral-900"></div>
        <div class="border-r border-neutral-100 dark:border-neutral-900"></div>
        <div class="hidden md:block border-r border-neutral-100 dark:border-neutral-900"></div>
        <div class="hidden md:block"></div>
      </div>

      <!-- Основной контент -->
      <div class="relative z-10 px-6 md:px-8 lg:px-12 xl:px-16">
        <div class="max-w-7xl mx-auto">
          <!-- Hero контент -->
          <div class="pt-16 md:pt-24 lg:pt-32 pb-16 md:pb-24">
            <div class="grid lg:grid-cols-12 gap-8 lg:gap-16 items-center">
              <!-- Левая колонка - основной контент -->
              <div class="lg:col-span-8 space-y-8 md:space-y-12">
                <!-- Заголовок -->
                <div class="space-y-6 md:space-y-8">
                  <h1
                    class="text-4xl md:text-5xl lg:text-6xl xl:text-7xl leading-[1.05] tracking-tight text-black dark:text-white font-light"
                  >
                    Мы создаем
                    <span class="relative inline-block text-[#FF3B30] font-medium">
                      цифровые
                      <span
                        class="absolute bottom-1 left-0 w-full h-[3px] bg-[#FF3B30] opacity-20"
                      ></span>
                    </span>
                    продукты, которые помогают бизнесу расти
                  </h1>

                  <p
                    class="text-lg md:text-xl lg:text-2xl text-neutral-600 dark:text-neutral-300 max-w-2xl leading-relaxed"
                  >
                    Разрабатываем сайты и приложения с современным дизайном и продуманным
                    пользовательским опытом
                  </p>
                </div>

                <!-- CTA кнопки -->
                <div class="flex flex-col sm:flex-row gap-4 sm:gap-6 pt-4">
                  <button
                    @click="scrollToProjects"
                    class="group inline-flex items-center justify-center px-8 py-4 bg-[#FF3B30] hover:bg-[#E6332A] text-white rounded-full transition-all duration-300 hover:scale-105 focus:outline-none focus:ring-2 focus:ring-[#FF3B30] focus:ring-offset-2 dark:focus:ring-offset-black"
                  >
                    <span class="font-medium">Смотреть работы</span>
                    <svg
                      class="ml-2 w-5 h-5 group-hover:translate-x-1 transition-transform"
                      viewBox="0 0 24 24"
                      fill="none"
                      stroke="currentColor"
                      stroke-width="2"
                    >
                      <path d="M5 12h14M12 5l7 7-7 7" />
                    </svg>
                  </button>

                  <button
                    class="inline-flex items-center justify-center px-8 py-4 border border-neutral-300 dark:border-neutral-700 hover:border-neutral-400 dark:hover:border-neutral-600 text-neutral-900 dark:text-neutral-100 rounded-full transition-all duration-300 hover:bg-neutral-50 dark:hover:bg-neutral-900 focus:outline-none focus:ring-2 focus:ring-neutral-300 dark:focus:ring-neutral-700 focus:ring-offset-2 dark:focus:ring-offset-black"
                  >
                    <span class="font-medium">Обсудить проект</span>
                  </button>
                </div>
              </div>

              <!-- Правая колонка - дополнительная информация -->
              <div class="lg:col-span-4 space-y-8">
                <div class="bg-neutral-50 dark:bg-neutral-900 rounded-2xl p-6 md:p-8">
                  <h3 class="text-lg font-medium text-neutral-900 dark:text-neutral-100 mb-4">
                    Наши принципы
                  </h3>
                  <ul class="space-y-3 text-neutral-600 dark:text-neutral-400">
                    <li class="flex items-start gap-3">
                      <div class="w-1.5 h-1.5 bg-[#FF3B30] rounded-full mt-2 flex-shrink-0"></div>
                      <span>Фокус на пользователе</span>
                    </li>
                    <li class="flex items-start gap-3">
                      <div class="w-1.5 h-1.5 bg-[#FF3B30] rounded-full mt-2 flex-shrink-0"></div>
                      <span>Современные технологии</span>
                    </li>
                    <li class="flex items-start gap-3">
                      <div class="w-1.5 h-1.5 bg-[#FF3B30] rounded-full mt-2 flex-shrink-0"></div>
                      <span>Масштабируемость</span>
                    </li>
                  </ul>
                </div>
              </div>
            </div>
          </div>

          <!-- Логотипы компаний -->
          <div class="py-12 md:py-16 border-t border-neutral-200 dark:border-neutral-800">
            <CompanyLogos />
          </div>

          <!-- Статистика -->
          <div class="py-12 md:py-16 border-t border-neutral-200 dark:border-neutral-800">
            <div class="grid grid-cols-2 lg:grid-cols-4 gap-8 lg:gap-12">
              <div class="text-center lg:text-left">
                <div
                  class="text-3xl md:text-4xl lg:text-5xl font-light tracking-tight text-black dark:text-white mb-2"
                >
                  50+
                </div>
                <div
                  class="text-sm md:text-base text-neutral-500 dark:text-neutral-400 uppercase tracking-wider"
                >
                  Проектов
                </div>
              </div>

              <div class="text-center lg:text-left">
                <div
                  class="text-3xl md:text-4xl lg:text-5xl font-light tracking-tight text-black dark:text-white mb-2"
                >
                  98%
                </div>
                <div
                  class="text-sm md:text-base text-neutral-500 dark:text-neutral-400 uppercase tracking-wider"
                >
                  Довольных клиентов
                </div>
              </div>

              <div class="text-center lg:text-left">
                <div
                  class="text-3xl md:text-4xl lg:text-5xl font-light tracking-tight text-black dark:text-white mb-2"
                >
                  15+
                </div>
                <div
                  class="text-sm md:text-base text-neutral-500 dark:text-neutral-400 uppercase tracking-wider"
                >
                  Лет опыта
                </div>
              </div>

              <div
                class="text-center lg:text-left col-span-2 lg:col-span-1 flex flex-col items-center lg:items-start justify-center"
              >
                <button
                  @click="scrollToProjects"
                  class="group inline-flex items-center gap-3 text-sm md:text-base font-medium tracking-wider text-neutral-900 dark:text-neutral-100 hover:text-[#FF3B30] dark:hover:text-[#FF3B30] transition-colors duration-300"
                >
                  <span>ПОРТФОЛИО</span>
                  <div
                    class="w-8 h-8 rounded-full border border-current group-hover:bg-[#FF3B30] group-hover:border-[#FF3B30] group-hover:text-white transition-all duration-300 flex items-center justify-center"
                  >
                    <svg
                      class="w-4 h-4"
                      viewBox="0 0 24 24"
                      fill="none"
                      stroke="currentColor"
                      stroke-width="2"
                    >
                      <path d="M7 17L17 7M17 7H7M17 7V17" />
                    </svg>
                  </div>
                </button>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import CompanyLogos from './CompanyLogos.vue'

const scrollToProjects = () => {
  const projectsSection = document.getElementById('projects')
  if (projectsSection) {
    projectsSection.scrollIntoView({ behavior: 'smooth' })
  }
}
</script>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&display=swap');

* {
  font-family:
    'Inter',
    system-ui,
    -apple-system,
    sans-serif;
}

.animate-marquee {
  animation: marquee 20s linear infinite;
  transform: translateX(100vw);
}

@keyframes marquee {
  0% {
    transform: translateX(100vw);
  }
  100% {
    transform: translateX(-100%);
  }
}

/* Улучшенная анимация для кнопок */
button {
  transform-origin: center;
}

button:active {
  transform: scale(0.98);
}

/* Плавные переходы для интерактивных элементов */
.group:hover .group-hover\:translate-x-1 {
  transform: translateX(0.25rem);
}
</style>
