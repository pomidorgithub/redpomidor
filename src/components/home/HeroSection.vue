<template>
  <section class="h-[calc(100vh-72px)] bg-neutral-50 dark:bg-neutral-950">
    <div class="h-full">
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
          <div class="h-full pl-7 pr-12 md:px-16 pt-12 md:pt-16 pb-12 md:pb-16 flex flex-col">
            <div class="flex-1 flex flex-col justify-center max-w-5xl">
              <div class="space-y-16">
                <div class="text-sm tracking-[0.2em] text-neutral-400">DIGITAL AGENCY</div>
                
                <div class="space-y-8">
                  <h1 class="text-4xl md:text-5xl lg:text-6xl leading-[1.1] tracking-tight">
                    Мы создаем цифровые продукты, которые помогают бизнесу расти
                  </h1>
                  
                  <p class="text-lg text-neutral-500 dark:text-neutral-400 max-w-xl">
                    Разрабатываем сайты и приложения с современным дизайном и продуманным пользовательским опытом
                  </p>
                </div>
              </div>
            </div>

            <!-- Статистика -->
            <div class="grid grid-cols-4 border-t border-neutral-200 dark:border-neutral-800 py-12">
              <div>
                <div class="text-3xl md:text-4xl font-light tracking-tight">50+</div>
                <div class="text-sm text-neutral-500">Проектов</div>
              </div>
              <div>
                <div class="text-3xl md:text-4xl font-light tracking-tight">98%</div>
                <div class="text-sm text-neutral-500">Клиентов</div>
              </div>
              <div>
                <div class="text-3xl md:text-4xl font-light tracking-tight">15+</div>
                <div class="text-sm text-neutral-500">Лет опыта</div>
              </div>
              <div class="flex items-center justify-end">
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

<style>
@import url('https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@300;500;700&display=swap');
</style>
