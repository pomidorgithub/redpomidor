<template>
  <section class="py-24 w-full">
    <div class="w-full px-8">
      <div class="max-w-[90rem] mx-auto">
        <!-- Заголовок секции -->
        <div class="mb-24 flex flex-col md:flex-row justify-between items-start md:items-end">
          <div class="space-y-4 mb-8 md:mb-0">
            <div class="text-sm tracking-[0.2em] text-neutral-500 dark:text-neutral-400">
              [ ПОРТФОЛИО ]
            </div>
            <h2 class="text-4xl md:text-6xl font-light">
              ИЗБРАННЫЕ<br/>ПРОЕКТЫ
            </h2>
          </div>
          <button class="border border-current px-8 py-3 text-sm tracking-[0.2em] hover:bg-black hover:text-white dark:hover:bg-white dark:hover:text-black transition-colors">
            [ ВСЕ РАБОТЫ ]
          </button>
        </div>

        <!-- Сетка проектов -->
        <div class="space-y-32">
          <!-- Проект 1 -->
          <div class="group">
            <div class="relative aspect-[16/9] overflow-hidden bg-neutral-100 dark:bg-neutral-900">
              <img 
                src="https://images.unsplash.com/photo-1618005182384-a83a8bd57fbe?w=1800&auto=format&fit=crop&q=80"
                alt="Architectural Project"
                class="w-full h-full object-cover transition-transform duration-700 group-hover:scale-105"
              />
              <div class="absolute inset-0 bg-gradient-to-t from-black/70 to-transparent opacity-0 group-hover:opacity-100 transition-opacity duration-300" />
            </div>
            <div class="mt-8 grid grid-cols-1 md:grid-cols-[1fr,2fr] gap-8 items-start">
              <div class="space-y-4">
                <div class="text-sm tracking-[0.2em] text-neutral-500 dark:text-neutral-400">[ АРХИТЕКТУРА ]</div>
                <div class="text-2xl font-light">Жилой комплекс премиум класса</div>
              </div>
              <div class="text-neutral-500 dark:text-neutral-400">
                Разработка архитектурной концепции и полного комплекта проектной документации для жилого комплекса в центре города
              </div>
            </div>
          </div>

          <!-- Проект 2 -->
          <div class="group">
            <div class="relative aspect-[16/9] overflow-hidden bg-neutral-100 dark:bg-neutral-900">
              <img 
                src="https://images.unsplash.com/photo-1600607687939-ce8a6c25118c?w=1800&auto=format&fit=crop&q=80"
                alt="Interior Design"
                class="w-full h-full object-cover transition-transform duration-700 group-hover:scale-105"
              />
              <div class="absolute inset-0 bg-gradient-to-t from-black/70 to-transparent opacity-0 group-hover:opacity-100 transition-opacity duration-300" />
            </div>
            <div class="mt-8 grid grid-cols-1 md:grid-cols-[1fr,2fr] gap-8 items-start">
              <div class="space-y-4">
                <div class="text-sm tracking-[0.2em] text-neutral-500 dark:text-neutral-400">[ ИНТЕРЬЕР ]</div>
                <div class="text-2xl font-light">Дизайн интерьера ресторана</div>
              </div>
              <div class="text-neutral-500 dark:text-neutral-400">
                Создание уникального интерьера для ресторана высокой кухни, включая проработку всех деталей и подбор материалов
              </div>
            </div>
          </div>

          <!-- Проект 3 -->
          <div class="group">
            <div class="relative aspect-[16/9] overflow-hidden bg-neutral-100 dark:bg-neutral-900">
              <img 
                src="https://images.unsplash.com/photo-1616627547584-bf28cee262db?w=1800&auto=format&fit=crop&q=80"
                alt="Furniture Design"
                class="w-full h-full object-cover transition-transform duration-700 group-hover:scale-105"
              />
              <div class="absolute inset-0 bg-gradient-to-t from-black/70 to-transparent opacity-0 group-hover:opacity-100 transition-opacity duration-300" />
            </div>
            <div class="mt-8 grid grid-cols-1 md:grid-cols-[1fr,2fr] gap-8 items-start">
              <div class="space-y-4">
                <div class="text-sm tracking-[0.2em] text-neutral-500 dark:text-neutral-400">[ МЕБЕЛЬ ]</div>
                <div class="text-2xl font-light">Коллекция авторской мебели</div>
              </div>
              <div class="text-neutral-500 dark:text-neutral-400">
                Разработка эксклюзивной коллекции мебели для международной выставки, включая прототипирование и подготовку к производству
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
// Projects section component
</script>
