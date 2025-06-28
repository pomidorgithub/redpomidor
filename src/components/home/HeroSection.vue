<template>
  <section class="relative h-screen bg-white dark:bg-black overflow-hidden">
    <!-- Animated background elements -->
    <div class="absolute inset-0">
      <!-- Floating particles -->
      <div class="absolute top-1/4 left-1/4 w-1 h-1 bg-[#FF3B30] rounded-full animate-pulse"></div>
      <div
        class="absolute top-3/4 left-1/3 w-0.5 h-0.5 bg-neutral-400 rounded-full animate-pulse delay-1000"
      ></div>
      <div
        class="absolute top-1/2 right-1/4 w-0.5 h-0.5 bg-[#FF3B30] rounded-full animate-pulse delay-2000"
      ></div>

      <!-- Subtle grid -->
      <div class="absolute inset-0 opacity-[0.02]">
        <div class="grid grid-cols-12 h-full">
          <div v-for="i in 12" :key="i" class="border-r border-neutral-500"></div>
        </div>
      </div>
    </div>

    <!-- Main content -->
    <div class="relative z-10 h-full flex items-center">
      <div class="page-padding w-full">
        <div class="grid grid-cols-12 gap-8">
          <!-- Main content - spans 9 columns -->
          <div class="col-span-9 space-y-20">
            <!-- Typography focus with animations -->
            <div class="space-y-16">
              <!-- Main heading with hover effects -->
              <h1
                class="text-7xl md:text-8xl lg:text-9xl font-black leading-[0.8] tracking-tighter text-neutral-900 dark:text-white group cursor-default"
              >
                <span class="inline-block hover:scale-105 transition-transform duration-300"
                  >DIGITAL</span
                ><br />
                <span
                  class="text-[#FF3B30] inline-block hover:scale-105 transition-transform duration-300 hover:rotate-1"
                  >CRAFT</span
                >
              </h1>

              <!-- Enhanced description -->
              <div class="max-w-lg space-y-8">
                <p class="text-xl text-neutral-600 dark:text-neutral-400 leading-relaxed">
                  Создаем цифровые продукты нового поколения с фокусом на
                  <span class="text-[#FF3B30] font-medium">пользовательский опыт</span>
                  и современные технологии
                </p>

                <!-- Interactive CTA section -->
                <div class="flex items-center gap-12">
                  <button
                    @click="scrollToProjects"
                    class="group flex items-center gap-4 text-neutral-900 dark:text-white hover:text-[#FF3B30] transition-all duration-300"
                  >
                    <div class="flex items-center gap-3 font-medium text-lg">
                      <span>2012</span>
                      <div class="w-16 h-px bg-current"></div>
                      <span>2025</span>
                    </div>
                    <div class="flex items-center gap-2">
                      <div
                        class="w-8 h-px bg-current group-hover:w-12 transition-all duration-300"
                      ></div>
                      <div
                        class="w-1 h-1 bg-current rounded-full group-hover:scale-150 transition-transform duration-300"
                      ></div>
                    </div>
                  </button>

                  <!-- Live counter -->
                  <div class="flex items-center gap-3 text-sm text-neutral-500">
                    <div class="w-2 h-2 bg-green-400 rounded-full animate-pulse"></div>
                    <span>Online • 2024</span>
                  </div>
                </div>
              </div>
            </div>

            <!-- Enhanced bottom stats -->
            <div class="flex items-end justify-between">
              <!-- Stats with hover effects -->
              <div class="group cursor-pointer">
                <div
                  class="text-5xl font-light text-neutral-900 dark:text-white group-hover:text-[#FF3B30] transition-colors duration-300"
                >
                  50<span class="text-2xl">+</span>
                </div>
                <div class="text-xs uppercase tracking-wider text-neutral-500 mt-2">
                  Projects Completed
                </div>
                <div
                  class="w-0 group-hover:w-full h-px bg-[#FF3B30] transition-all duration-500 mt-1"
                ></div>
              </div>

              <div class="group cursor-pointer">
                <div
                  class="text-5xl font-light text-[#FF3B30] group-hover:scale-110 transition-transform duration-300"
                >
                  98<span class="text-2xl">%</span>
                </div>
                <div class="text-xs uppercase tracking-wider text-neutral-500 mt-2">
                  Success Rate
                </div>
                <div
                  class="w-0 group-hover:w-full h-px bg-[#FF3B30] transition-all duration-500 mt-1"
                ></div>
              </div>

              <div class="group cursor-pointer">
                <div
                  class="text-5xl font-light text-neutral-900 dark:text-white group-hover:text-[#FF3B30] transition-colors duration-300"
                >
                  15<span class="text-2xl">+</span>
                </div>
                <div class="text-xs uppercase tracking-wider text-neutral-500 mt-2">
                  Years Experience
                </div>
                <div
                  class="w-0 group-hover:w-full h-px bg-[#FF3B30] transition-all duration-500 mt-1"
                ></div>
              </div>
            </div>
          </div>

          <!-- Right sidebar - 3 columns -->
          <div class="col-span-3 flex flex-col justify-between py-8">
            <!-- Top accent -->
            <div class="space-y-8">
              <div class="text-right">
                <div class="text-xs text-neutral-400">#001</div>
                <div class="text-xs text-neutral-500 mt-1">Portfolio</div>
              </div>

              <!-- Vertical progress indicator -->
              <div class="ml-auto w-px h-32 bg-neutral-200 dark:bg-neutral-800 relative">
                <div class="absolute top-0 left-0 w-full h-1/3 bg-[#FF3B30] animate-pulse"></div>
              </div>
            </div>

            <!-- Bottom info -->
            <div class="space-y-6 text-right">
              <!-- Social proof -->
              <div class="space-y-2">
                <div class="text-sm text-neutral-600 dark:text-neutral-400">Trusted by</div>
                <div class="text-xs text-neutral-500">
                  Tinkoff • Rosbank<br />
                  Sovcombank • Almapark
                </div>
              </div>

              <!-- Contact hint -->
              <button
                class="text-xs text-neutral-500 hover:text-[#FF3B30] transition-colors duration-300 group"
              >
                <span>Discuss Project</span>
                <div
                  class="w-0 group-hover:w-full h-px bg-[#FF3B30] transition-all duration-300 mt-1 ml-auto"
                ></div>
              </button>
            </div>
          </div>
        </div>
      </div>
    </div>

    <!-- Floating action button -->
    <div class="absolute bottom-8 right-8">
      <button
        @click="scrollToProjects"
        class="w-12 h-12 bg-[#FF3B30] hover:bg-red-600 text-white rounded-full flex items-center justify-center group transition-all duration-300 hover:scale-110 shadow-lg hover:shadow-xl"
      >
        <svg
          class="w-4 h-4 group-hover:translate-y-0.5 transition-transform duration-300"
          viewBox="0 0 16 16"
          fill="currentColor"
        >
          <path d="M8 1v14M1 8h14" />
        </svg>
      </button>
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

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Inter:wght@200;300;400;500;900&display=swap');

* {
  font-family:
    'Inter',
    system-ui,
    -apple-system,
    sans-serif;
}

button:active {
  transform: scale(0.98);
}

/* Custom animations */
@keyframes float {
  0%,
  100% {
    transform: translateY(0px);
  }
  50% {
    transform: translateY(-10px);
  }
}

.animate-float {
  animation: float 3s ease-in-out infinite;
}

/* Hover enhancements */
.group:hover .group-hover\:scale-110 {
  transform: scale(1.1);
}

.group:hover .group-hover\:rotate-1 {
  transform: rotate(1deg);
}
</style>
