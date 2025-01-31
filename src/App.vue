<template>
  <!-- 
    App root
    Содержит:
    - DefaultLayout: базовая структура сайта
    - Sidebar: выезжающее меню
    - Другие глобальные компоненты
  -->
  <div class="min-h-screen bg-white text-black dark:bg-black dark:text-white">
    <DefaultLayout @toggle-sidebar="isSidebarOpen = !isSidebarOpen">
      <router-view />
    </DefaultLayout>
    
    <!-- Глобальные компоненты -->
    <Sidebar 
      :is-open="isSidebarOpen" 
      @close="isSidebarOpen = false"
    />

    <CookieConsent />
  </div>
</template>

<script setup>
import { ref } from 'vue'
import DefaultLayout from './components/layout/DefaultLayout.vue'
import Sidebar from './components/layout/Sidebar.vue'
import CookieConsent from './components/common/CookieConsent.vue'

const isSidebarOpen = ref(false)
</script>
