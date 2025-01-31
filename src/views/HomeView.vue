<template>
  <!-- 
    Home page
    Содержит только компоненты страницы,
    вся структура находится в DefaultLayout
  -->
  <div>
    <HeroSection />
    <ProjectsSection />
  </div>
</template>

<script setup>
import HeroSection from '../components/home/HeroSection.vue'
import ProjectsSection from '../components/home/ProjectsSection.vue'
</script>
