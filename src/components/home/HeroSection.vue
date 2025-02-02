<template>
  <section class="h-[calc(100vh-72px)] bg-white dark:bg-black overflow-x-hidden">
    <div class="h-full relative">
      <!-- Фоновая сетка -->
      <div class="absolute inset-0 grid grid-cols-2 md:grid-cols-4">
        <div></div>
        <div></div>
        <div class="hidden md:block"></div>
        <div class="hidden md:block"></div>
      </div>

      <!-- Контент -->
      <div class="h-full">
        <div class="h-full">
          <!-- Основная колонка -->
          <div class="h-full px-8 pt-12 md:pt-16 pb-12 md:pb-16 flex flex-col overflow-x-hidden">
            <div class="flex-1 flex flex-col justify-center max-w-5xl">
              <div class="space-y-8">
                <div class="space-y-8">
                  <h1
                    class="text-4xl md:text-5xl lg:text-6xl leading-[1.1] tracking-tight text-black dark:text-white"
                  >
                    Мы создаем
                    <span class="relative text-[#FF3B30]"
                      >цифровые
                      <span class="absolute bottom-1 left-0 w-full h-[2px] bg-[#FF3B30]"></span>
                    </span>
                    продукты, которые помогают бизнесу расти
                  </h1>

                  <p class="text-xl text-neutral-500 dark:text-neutral-400 max-w-xl">
                    Разрабатываем сайты и приложения с современным дизайном и продуманным
                    пользовательским опытом
                  </p>
                </div>
              </div>
            </div>

            <div class="mt-auto md:mt-24">
              <CompanyLogos />
            </div>

            <!-- Статистика -->
            <div class="mt-16 border-t border-neutral-200 dark:border-neutral-800 py-8 md:py-12">
              <div class="grid grid-cols-2 md:grid-cols-4 gap-8 md:gap-0">
                <div>
                  <div class="text-2xl md:text-3xl lg:text-4xl font-light tracking-tight">50+</div>
                  <div class="text-sm text-neutral-500">Проектов</div>
                </div>
                <div>
                  <div class="text-2xl md:text-3xl lg:text-4xl font-light tracking-tight">98%</div>
                  <div class="text-sm text-neutral-500">Клиентов</div>
                </div>
                <div>
                  <div class="text-2xl md:text-3xl lg:text-4xl font-light tracking-tight">15+</div>
                  <div class="text-sm text-neutral-500">Лет опыта</div>
                </div>
                <div
                  class="col-span-2 md:col-span-1 flex items-center justify-start md:justify-end pt-8 md:pt-0"
                >
                  <button
                    @click="scrollToProjects"
                    class="group relative inline-flex items-center gap-6 text-sm tracking-[0.2em] hover:text-neutral-500 transition-colors"
                  >
                    <span class="relative z-10">СМОТРЕТЬ РАБОТЫ</span>
                    <div
                      class="relative w-10 h-10 rounded-full border border-current group-hover:bg-[#FF3B30] group-hover:border-[#FF3B30] dark:group-hover:bg-[#FF3B30] dark:group-hover:border-[#FF3B30] transition-colors"
                    >
                      <svg
                        class="absolute inset-0 m-auto w-5 h-5 group-hover:text-white dark:group-hover:text-white transition-colors"
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
@import url('https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@300;500;700&display=swap');

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
</style>
