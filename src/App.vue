<template>
  <!-- 
    App root
    Содержит:
    - DefaultLayout: базовая структура сайта
    - Sidebar: выезжающее меню
    - Другие глобальные компоненты
  -->
  <div class="min-h-screen">
    <DefaultLayout @toggle-sidebar="isSidebarOpen = !isSidebarOpen">
      <router-view />
    </DefaultLayout>
    
    <!-- Глобальные компоненты -->
    <Sidebar 
      :is-open="isSidebarOpen" 
      @close="isSidebarOpen = false"
    />
  </div>
</template>

<script setup>
import { ref } from 'vue'
import DefaultLayout from './components/layout/DefaultLayout.vue'
import Sidebar from './components/layout/Sidebar.vue'

const isSidebarOpen = ref(false)
</script>
