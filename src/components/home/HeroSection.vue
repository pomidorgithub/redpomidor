<template>
  <section
    class="min-h-[calc(100vh-72px)] flex items-center justify-center w-full relative bg-neutral-50 dark:bg-neutral-950"
    :class="{ 'is-dark': isDark }"
  >
    <div class="w-full px-8 relative z-10">
      <div
        class="max-w-[90rem] mx-auto grid grid-cols-1 md:grid-cols-[1fr,auto] items-center gap-16"
      >
        <!-- Основной контент -->
        <div
          class="max-w-4xl space-y-8"
          v-motion
          :initial="{ opacity: 0, y: 100 }"
          :enter="{ opacity: 1, y: 0 }"
          :delay="200"
        >
          <div class="space-y-4">
            <div class="text-sm tracking-[0.2em] text-neutral-500 dark:text-neutral-400">
              [ ВЕБ-СТУДИЯ ]
            </div>
            <h1 class="text-4xl md:text-7xl font-light">
              СОЗДАЁМ<br />
              ЦИФРОВЫЕ<br />
              ПРОДУКТЫ
            </h1>
          </div>

          <div class="text-neutral-500 dark:text-neutral-400 max-w-xl">
            Мы разрабатываем современные веб-сайты и приложения, которые помогают бизнесу расти в
            цифровом пространстве.
          </div>

          <!-- Статистика -->
          <div
            class="grid grid-cols-3 gap-8 py-8 border-y border-neutral-200 dark:border-neutral-800"
          >
            <div class="space-y-2">
              <div
                class="text-3xl font-light"
                v-motion
                :initial="{ opacity: 0 }"
                :enter="{ opacity: 1 }"
                :delay="600"
              >
                50+
              </div>
              <div class="text-sm tracking-[0.2em] text-neutral-500 dark:text-neutral-400">
                [ ПРОЕКТОВ ]
              </div>
            </div>
            <div class="space-y-2">
              <div
                class="text-3xl font-light"
                v-motion
                :initial="{ opacity: 0 }"
                :enter="{ opacity: 1 }"
                :delay="800"
              >
                98%
              </div>
              <div class="text-sm tracking-[0.2em] text-neutral-500 dark:text-neutral-400">
                [ КЛИЕНТОВ ]
              </div>
            </div>
            <div class="space-y-2">
              <div
                class="text-3xl font-light"
                v-motion
                :initial="{ opacity: 0 }"
                :enter="{ opacity: 1 }"
                :delay="1000"
              >
                15+
              </div>
              <div class="text-sm tracking-[0.2em] text-neutral-500 dark:text-neutral-400">
                [ ЛЕТ ]
              </div>
            </div>
          </div>

          <button
            @click="scrollToProjects"
            class="border border-current px-8 py-3 text-sm tracking-[0.2em] hover:bg-black hover:text-white dark:hover:bg-white dark:hover:text-black transition-colors"
          >
            [ СМОТРЕТЬ РАБОТЫ ]
          </button>
        </div>

        <!-- Декоративный элемент справа -->
        <div
          class="hidden md:flex flex-col items-end space-y-8 text-sm tracking-[0.2em]"
          v-motion
          :initial="{ opacity: 0, x: 50 }"
          :enter="{ opacity: 1, x: 0 }"
          :delay="400"
        >
          <div class="text-neutral-400 dark:text-neutral-600 text-right">[ EST. 2024 ]</div>
          <div class="h-32 w-[1px] bg-neutral-200 dark:bg-neutral-800"></div>
          <div class="text-neutral-400 dark:text-neutral-600 text-right">
            [ САЙТЫ ]<br />
            [ ПРИЛОЖЕНИЯ ]<br />
            [ E-COMMERCE ]
          </div>
          <div class="h-32 w-[1px] bg-neutral-200 dark:bg-neutral-800"></div>
          <div class="text-neutral-400 dark:text-neutral-600 text-right">
            [ REACT ]<br />
            [ VUE ]<br />
            [ NODE ]
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
