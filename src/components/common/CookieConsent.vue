<template>
  <div 
    v-if="!accepted"
    class="fixed bottom-0 left-0 right-0 bg-white dark:bg-black border-t border-neutral-200 dark:border-neutral-800 p-4 z-50"
    v-motion
    :initial="{ opacity: 0, y: 100 }"
    :enter="{ opacity: 1, y: 0 }"
  >
    <div class="max-w-[90rem] mx-auto px-8 flex flex-col md:flex-row justify-between items-start md:items-center gap-4">
      <div class="space-y-2">
        <div class="text-sm tracking-[0.2em] text-neutral-500 dark:text-neutral-400">
          [ COOKIES ]
        </div>
        <div class="text-sm max-w-2xl">
          Мы используем файлы cookie для анализа данных и персонализации вашего опыта.
        </div>
      </div>
      <div class="flex gap-4">
        <button 
          @click="accept"
          class="border border-current px-8 py-3 text-sm tracking-[0.2em] hover:bg-black hover:text-white dark:hover:bg-white dark:hover:text-black transition-colors"
        >
          [ ПРИНЯТЬ ]
        </button>
        <button 
          @click="decline"
          class="px-8 py-3 text-sm tracking-[0.2em] text-neutral-500 hover:text-black dark:hover:text-white transition-colors"
        >
          [ ОТКЛОНИТЬ ]
        </button>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref, onMounted } from 'vue'

const accepted = ref(false)

onMounted(() => {
  accepted.value = localStorage.getItem('cookiesAccepted') === 'true'
})

const accept = () => {
  localStorage.setItem('cookiesAccepted', 'true')
  accepted.value = true
}

const decline = () => {
  localStorage.setItem('cookiesAccepted', 'false')
  accepted.value = true
}
</script>
