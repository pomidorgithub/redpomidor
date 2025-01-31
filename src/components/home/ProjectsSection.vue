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
            <h2 class="text-4xl md:text-6xl font-light">ИЗБРАННЫЕ<br />ПРОЕКТЫ</h2>
          </div>
          <button
            class="border border-current px-8 py-3 text-sm tracking-[0.2em] hover:bg-black hover:text-white dark:hover:bg-white dark:hover:text-black transition-colors"
          >
            [ ВСЕ РАБОТЫ ]
          </button>
        </div>

        <!-- Сетка проектов -->
        <div class="space-y-32">
          <!-- Проект 1 -->
          <div 
            class="group cursor-pointer"
            v-motion
            :initial="{ opacity: 0 }"
            :visible="{ 
              opacity: 1,
              transition: {
                duration: 1000,
                ease: 'easeOut'
              }
            }"
            @click="$router.push('/projects/1')"
          >
            <div class="relative aspect-[16/5] overflow-hidden bg-neutral-100 dark:bg-neutral-900">
              <img
                src="https://images.unsplash.com/photo-1486312338219-ce68d2c6f44d?w=1800&auto=format&fit=crop&q=80"
                alt="Web Development Project"
                class="w-full h-full object-cover transition-transform duration-700 group-hover:scale-105"
              />
              <div
                class="absolute inset-0 bg-gradient-to-t from-black/70 to-transparent opacity-100 group-hover:opacity-0 transition-opacity duration-300"
              />
            </div>
            <div class="mt-8 grid grid-cols-1 md:grid-cols-[1fr,2fr] gap-8 items-start">
              <div class="space-y-4">
                <div class="text-sm tracking-[0.2em] text-neutral-500 dark:text-neutral-400">
                  [ КОРПОРАТИВНЫЙ САЙТ ]
                </div>
                <div class="text-2xl font-light">Многостраничный сайт для IT компании</div>
              </div>
              <div class="text-neutral-500 dark:text-neutral-400">
                Разработка современного корпоративного сайта с анимациями и
                интерактивными элементами. Адаптивный дизайн для всех устройств.
              </div>
            </div>
          </div>

          <!-- Проект 2 -->
          <div 
            class="group cursor-pointer"
            v-motion
            :initial="{ opacity: 0 }"
            :visible="{ 
              opacity: 1,
              transition: {
                duration: 1000,
                ease: 'easeOut'
              }
            }"
            @click="$router.push('/projects/2')"
          >
            <div class="relative aspect-[16/5] overflow-hidden bg-neutral-100 dark:bg-neutral-900">
              <img
                src="https://images.unsplash.com/photo-1551650975-87deedd944c3?w=1800&auto=format&fit=crop&q=80"
                alt="E-commerce Project"
                class="w-full h-full object-cover transition-transform duration-700 group-hover:scale-105"
              />
              <div
                class="absolute inset-0 bg-gradient-to-t from-black/70 to-transparent opacity-100 group-hover:opacity-0 transition-opacity duration-300"
              />
            </div>
            <div class="mt-8 grid grid-cols-1 md:grid-cols-[1fr,2fr] gap-8 items-start">
              <div class="space-y-4">
                <div class="text-sm tracking-[0.2em] text-neutral-500 dark:text-neutral-400">
                  [ E-COMMERCE ]
                </div>
                <div class="text-2xl font-light">Интернет-магазин электроники</div>
              </div>
              <div class="text-neutral-500 dark:text-neutral-400">
                Создание масштабируемого интернет-магазина с каталогом товаров,
                фильтрацией и системой оплаты. Интеграция с 1С и CRM.
              </div>
            </div>
          </div>

          <!-- Проект 3 -->
          <div 
            class="group cursor-pointer"
            v-motion
            :initial="{ opacity: 0 }"
            :visible="{ 
              opacity: 1,
              transition: {
                duration: 1000,
                ease: 'easeOut'
              }
            }"
            @click="$router.push('/projects/3')"
          >
            <div class="relative aspect-[16/5] overflow-hidden bg-neutral-100 dark:bg-neutral-900">
              <img
                src="https://images.unsplash.com/photo-1555774698-0b77e0d5fac6?w=1800&auto=format&fit=crop&q=80"
                alt="Web App Project"
                class="w-full h-full object-cover transition-transform duration-700 group-hover:scale-105"
              />
              <div
                class="absolute inset-0 bg-gradient-to-t from-black/70 to-transparent opacity-100 group-hover:opacity-0 transition-opacity duration-300"
              />
            </div>
            <div class="mt-8 grid grid-cols-1 md:grid-cols-[1fr,2fr] gap-8 items-start">
              <div class="space-y-4">
                <div class="text-sm tracking-[0.2em] text-neutral-500 dark:text-neutral-400">
                  [ ВЕБ-ПРИЛОЖЕНИЕ ]
                </div>
                <div class="text-2xl font-light">Система управления проектами</div>
              </div>
              <div class="text-neutral-500 dark:text-neutral-400">
                Разработка SaaS-приложения для управления проектами с real-time
                обновлениями и системой уведомлений. React + Node.js.
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
