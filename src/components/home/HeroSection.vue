<template>
  <section
    class="relative min-h-screen bg-gradient-to-br from-white via-neutral-50 to-neutral-100 dark:from-black dark:via-neutral-950 dark:to-neutral-900 overflow-hidden"
  >
    <!-- Animated background elements -->
    <div class="absolute inset-0">
      <!-- Floating circles -->
      <div
        class="absolute top-20 left-10 w-64 h-64 bg-[#FF3B30] opacity-5 rounded-full blur-3xl animate-float"
      ></div>
      <div
        class="absolute bottom-20 right-10 w-96 h-96 bg-blue-500 opacity-5 rounded-full blur-3xl animate-float-delayed"
      ></div>
      <div
        class="absolute top-1/2 left-1/3 w-48 h-48 bg-purple-500 opacity-5 rounded-full blur-3xl animate-float-slow"
      ></div>

      <!-- Grid pattern -->
      <div class="absolute inset-0 opacity-20">
        <div class="grid grid-cols-12 h-full">
          <div
            v-for="i in 12"
            :key="i"
            class="border-r border-neutral-200 dark:border-neutral-800"
          ></div>
        </div>
      </div>
    </div>

    <!-- Main content -->
    <div class="relative z-10">
      <div class="max-w-7xl mx-auto page-padding">
        <!-- Hero section -->
        <div class="pt-20 md:pt-32 lg:pt-40 pb-20">
          <div class="grid lg:grid-cols-12 gap-12 lg:gap-16">
            <!-- Main content column -->
            <div class="lg:col-span-7 space-y-10">
              <!-- Badge -->
              <div
                class="inline-flex items-center gap-2 px-4 py-2 bg-[#FF3B30]/10 dark:bg-[#FF3B30]/20 rounded-full border border-[#FF3B30]/20"
              >
                <div class="w-2 h-2 bg-[#FF3B30] rounded-full animate-pulse"></div>
                <span class="text-sm font-medium text-[#FF3B30]">Доступны для новых проектов</span>
              </div>

              <!-- Main heading -->
              <div class="space-y-6">
                <h1
                  class="text-5xl md:text-6xl lg:text-7xl xl:text-8xl leading-[0.9] tracking-tight font-bold"
                >
                  <span class="text-neutral-900 dark:text-white">Мы создаем</span>
                  <br />
                  <span class="relative inline-block">
                    <span
                      class="bg-gradient-to-r from-[#FF3B30] via-[#FF6B35] to-[#FF8E53] bg-clip-text text-transparent"
                    >
                      цифровые
                    </span>
                    <div
                      class="absolute -bottom-2 left-0 w-full h-1 bg-gradient-to-r from-[#FF3B30] to-[#FF8E53] rounded-full"
                    ></div>
                  </span>
                  <br />
                  <span class="text-neutral-900 dark:text-white">продукты</span>
                </h1>

                <p
                  class="text-xl md:text-2xl text-neutral-600 dark:text-neutral-300 max-w-2xl leading-relaxed font-light"
                >
                  Разрабатываем сайты и приложения с современным дизайном и продуманным
                  пользовательским опытом
                </p>
              </div>

              <!-- CTA buttons -->
              <div class="flex flex-col sm:flex-row gap-4 pt-6">
                <button
                  @click="scrollToProjects"
                  class="group relative overflow-hidden px-8 py-4 bg-gradient-to-r from-[#FF3B30] to-[#FF6B35] hover:from-[#E6332A] hover:to-[#E55A2F] text-white rounded-2xl transition-all duration-500 hover:scale-105 hover:shadow-2xl hover:shadow-[#FF3B30]/25 focus:outline-none focus:ring-2 focus:ring-[#FF3B30] focus:ring-offset-2 dark:focus:ring-offset-black"
                >
                  <span class="relative z-10 flex items-center justify-center gap-3 font-semibold">
                    Смотреть работы
                    <svg
                      class="w-5 h-5 group-hover:translate-x-1 transition-transform duration-300"
                      viewBox="0 0 24 24"
                      fill="none"
                      stroke="currentColor"
                      stroke-width="2"
                    >
                      <path d="M5 12h14M12 5l7 7-7 7" />
                    </svg>
                  </span>
                  <div
                    class="absolute inset-0 bg-gradient-to-r from-white/20 to-transparent opacity-0 group-hover:opacity-100 transition-opacity duration-500"
                  ></div>
                </button>

                <button
                  class="group px-8 py-4 border-2 border-neutral-300 dark:border-neutral-600 hover:border-[#FF3B30] dark:hover:border-[#FF3B30] text-neutral-900 dark:text-neutral-100 hover:text-[#FF3B30] dark:hover:text-[#FF3B30] rounded-2xl transition-all duration-300 hover:bg-[#FF3B30]/5 focus:outline-none focus:ring-2 focus:ring-neutral-300 dark:focus:ring-neutral-700 focus:ring-offset-2 dark:focus:ring-offset-black"
                >
                  <span class="font-semibold">Обсудить проект</span>
                </button>
              </div>

              <!-- Quick stats -->
              <div class="grid grid-cols-3 gap-8 pt-8">
                <div class="text-center sm:text-left">
                  <div class="text-3xl md:text-4xl font-bold text-neutral-900 dark:text-white mb-1">
                    50+
                  </div>
                  <div
                    class="text-sm text-neutral-500 dark:text-neutral-400 uppercase tracking-wider"
                  >
                    Проектов
                  </div>
                </div>
                <div class="text-center sm:text-left">
                  <div class="text-3xl md:text-4xl font-bold text-neutral-900 dark:text-white mb-1">
                    98%
                  </div>
                  <div
                    class="text-sm text-neutral-500 dark:text-neutral-400 uppercase tracking-wider"
                  >
                    Успеха
                  </div>
                </div>
                <div class="text-center sm:text-left">
                  <div class="text-3xl md:text-4xl font-bold text-neutral-900 dark:text-white mb-1">
                    15+
                  </div>
                  <div
                    class="text-sm text-neutral-500 dark:text-neutral-400 uppercase tracking-wider"
                  >
                    Лет
                  </div>
                </div>
              </div>
            </div>

            <!-- Side content -->
            <div class="lg:col-span-5 space-y-6">
              <!-- Feature cards -->
              <div class="grid gap-4">
                <div
                  class="group p-6 bg-white/60 dark:bg-neutral-900/60 backdrop-blur-sm rounded-2xl border border-neutral-200/50 dark:border-neutral-700/50 hover:border-[#FF3B30]/30 hover:bg-white/80 dark:hover:bg-neutral-900/80 transition-all duration-300 hover:scale-105"
                >
                  <div class="flex items-start gap-4">
                    <div
                      class="w-12 h-12 bg-gradient-to-br from-[#FF3B30] to-[#FF6B35] rounded-xl flex items-center justify-center flex-shrink-0"
                    >
                      <svg
                        class="w-6 h-6 text-white"
                        fill="none"
                        stroke="currentColor"
                        viewBox="0 0 24 24"
                      >
                        <path
                          stroke-linecap="round"
                          stroke-linejoin="round"
                          stroke-width="2"
                          d="M13 10V3L4 14h7v7l9-11h-7z"
                        />
                      </svg>
                    </div>
                    <div>
                      <h3 class="font-semibold text-neutral-900 dark:text-white mb-2">
                        Молниеносная скорость
                      </h3>
                      <p class="text-sm text-neutral-600 dark:text-neutral-400">
                        Оптимизированные решения для максимальной производительности
                      </p>
                    </div>
                  </div>
                </div>

                <div
                  class="group p-6 bg-white/60 dark:bg-neutral-900/60 backdrop-blur-sm rounded-2xl border border-neutral-200/50 dark:border-neutral-700/50 hover:border-[#FF3B30]/30 hover:bg-white/80 dark:hover:bg-neutral-900/80 transition-all duration-300 hover:scale-105"
                >
                  <div class="flex items-start gap-4">
                    <div
                      class="w-12 h-12 bg-gradient-to-br from-blue-500 to-blue-600 rounded-xl flex items-center justify-center flex-shrink-0"
                    >
                      <svg
                        class="w-6 h-6 text-white"
                        fill="none"
                        stroke="currentColor"
                        viewBox="0 0 24 24"
                      >
                        <path
                          stroke-linecap="round"
                          stroke-linejoin="round"
                          stroke-width="2"
                          d="M4.318 6.318a4.5 4.5 0 000 6.364L12 20.364l7.682-7.682a4.5 4.5 0 00-6.364-6.364L12 7.636l-1.318-1.318a4.5 4.5 0 00-6.364 0z"
                        />
                      </svg>
                    </div>
                    <div>
                      <h3 class="font-semibold text-neutral-900 dark:text-white mb-2">
                        Фокус на UX
                      </h3>
                      <p class="text-sm text-neutral-600 dark:text-neutral-400">
                        Каждое решение создается с мыслью о пользователе
                      </p>
                    </div>
                  </div>
                </div>

                <div
                  class="group p-6 bg-white/60 dark:bg-neutral-900/60 backdrop-blur-sm rounded-2xl border border-neutral-200/50 dark:border-neutral-700/50 hover:border-[#FF3B30]/30 hover:bg-white/80 dark:hover:bg-neutral-900/80 transition-all duration-300 hover:scale-105"
                >
                  <div class="flex items-start gap-4">
                    <div
                      class="w-12 h-12 bg-gradient-to-br from-purple-500 to-purple-600 rounded-xl flex items-center justify-center flex-shrink-0"
                    >
                      <svg
                        class="w-6 h-6 text-white"
                        fill="none"
                        stroke="currentColor"
                        viewBox="0 0 24 24"
                      >
                        <path
                          stroke-linecap="round"
                          stroke-linejoin="round"
                          stroke-width="2"
                          d="M9 12l2 2 4-4M7.835 4.697a3.42 3.42 0 001.946-.806 3.42 3.42 0 014.438 0 3.42 3.42 0 001.946.806 3.42 3.42 0 013.138 3.138 3.42 3.42 0 00.806 1.946 3.42 3.42 0 010 4.438 3.42 3.42 0 00-.806 1.946 3.42 3.42 0 01-3.138 3.138 3.42 3.42 0 00-1.946.806 3.42 3.42 0 01-4.438 0 3.42 3.42 0 00-1.946-.806 3.42 3.42 0 01-3.138-3.138 3.42 3.42 0 00-.806-1.946 3.42 3.42 0 010-4.438 3.42 3.42 0 00.806-1.946 3.42 3.42 0 013.138-3.138z"
                        />
                      </svg>
                    </div>
                    <div>
                      <h3 class="font-semibold text-neutral-900 dark:text-white mb-2">
                        Гарантия качества
                      </h3>
                      <p class="text-sm text-neutral-600 dark:text-neutral-400">
                        Тестируем каждую деталь перед запуском
                      </p>
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>

        <!-- Company logos section -->
        <div class="py-16 border-t border-neutral-200/50 dark:border-neutral-700/50">
          <div class="text-center mb-12">
            <p class="text-sm uppercase tracking-wider text-neutral-500 dark:text-neutral-400 mb-8">
              Нам доверяют
            </p>
            <CompanyLogos />
          </div>
        </div>

        <!-- Enhanced stats section -->
        <div class="py-16 border-t border-neutral-200/50 dark:border-neutral-700/50">
          <div class="grid grid-cols-2 lg:grid-cols-4 gap-8">
            <div class="text-center group">
              <div
                class="text-4xl md:text-5xl lg:text-6xl font-bold bg-gradient-to-r from-[#FF3B30] to-[#FF6B35] bg-clip-text text-transparent mb-3 group-hover:scale-110 transition-transform duration-300"
              >
                50+
              </div>
              <div class="text-base text-neutral-600 dark:text-neutral-400 font-medium">
                Успешных проектов
              </div>
            </div>

            <div class="text-center group">
              <div
                class="text-4xl md:text-5xl lg:text-6xl font-bold bg-gradient-to-r from-blue-500 to-blue-600 bg-clip-text text-transparent mb-3 group-hover:scale-110 transition-transform duration-300"
              >
                98%
              </div>
              <div class="text-base text-neutral-600 dark:text-neutral-400 font-medium">
                Довольных клиентов
              </div>
            </div>

            <div class="text-center group">
              <div
                class="text-4xl md:text-5xl lg:text-6xl font-bold bg-gradient-to-r from-purple-500 to-purple-600 bg-clip-text text-transparent mb-3 group-hover:scale-110 transition-transform duration-300"
              >
                15+
              </div>
              <div class="text-base text-neutral-600 dark:text-neutral-400 font-medium">
                Лет экспертизы
              </div>
            </div>

            <div class="text-center group col-span-2 lg:col-span-1">
              <button
                @click="scrollToProjects"
                class="inline-flex items-center gap-3 px-6 py-3 bg-neutral-900 dark:bg-white text-white dark:text-neutral-900 rounded-xl hover:bg-neutral-800 dark:hover:bg-neutral-100 transition-all duration-300 hover:scale-105 font-semibold"
              >
                <span>Портфолио</span>
                <svg
                  class="w-4 h-4"
                  viewBox="0 0 24 24"
                  fill="none"
                  stroke="currentColor"
                  stroke-width="2"
                >
                  <path d="M7 17L17 7M17 7H7M17 7V17" />
                </svg>
              </button>
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
@import url('https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700;800;900&display=swap');

* {
  font-family:
    'Inter',
    system-ui,
    -apple-system,
    sans-serif;
}

/* Floating animations */
@keyframes float {
  0%,
  100% {
    transform: translateY(0px) rotate(0deg);
  }
  50% {
    transform: translateY(-20px) rotate(5deg);
  }
}

@keyframes float-delayed {
  0%,
  100% {
    transform: translateY(0px) rotate(0deg);
  }
  50% {
    transform: translateY(-30px) rotate(-3deg);
  }
}

@keyframes float-slow {
  0%,
  100% {
    transform: translateY(0px) rotate(0deg);
  }
  50% {
    transform: translateY(-15px) rotate(2deg);
  }
}

.animate-float {
  animation: float 6s ease-in-out infinite;
}

.animate-float-delayed {
  animation: float-delayed 8s ease-in-out infinite;
  animation-delay: -2s;
}

.animate-float-slow {
  animation: float-slow 10s ease-in-out infinite;
  animation-delay: -4s;
}

/* Enhanced button interactions */
button {
  transform-origin: center;
}

button:active {
  transform: scale(0.95);
}

/* Smooth transitions */
.group:hover .group-hover\:translate-x-1 {
  transform: translateX(0.25rem);
}

/* Backdrop blur support */
.backdrop-blur-sm {
  backdrop-filter: blur(4px);
}

/* Custom scrollbar for webkit browsers */
::-webkit-scrollbar {
  width: 8px;
}

::-webkit-scrollbar-track {
  background: transparent;
}

::-webkit-scrollbar-thumb {
  background: rgba(255, 59, 48, 0.3);
  border-radius: 4px;
}

::-webkit-scrollbar-thumb:hover {
  background: rgba(255, 59, 48, 0.5);
}
</style>
