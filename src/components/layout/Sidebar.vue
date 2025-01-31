<template>
  <div
    class="fixed inset-0 bg-black transform transition-transform duration-500 origin-top z-[100]"
    :class="{ 'scale-y-0': !isOpen }"
  >
    <!-- Header с кнопкой закрытия -->
    <div class="py-3 px-4">
      <div class="flex justify-between items-center max-w-7xl mx-auto">
        <div class="flex items-center gap-2">
          <LogoIcon class="w-6 h-6" />
          <span class="text-sm tracking-[0.2em] text-white">[ REDPOMIDOR ]</span>
        </div>
        <button
          class="text-sm tracking-[0.2em] text-white hover:text-zinc-300 transition-colors duration-300"
          @click="$emit('close')"
        >
          [ CLOSE ]
        </button>
      </div>
    </div>

    <!-- Навигация -->
    <div class="flex flex-col h-[calc(100vh-80px)] justify-center items-center">
      <nav class="flex flex-col gap-8 text-[60px] font-light text-white text-center">
        <router-link
          to="/"
          class="hover:text-zinc-300 transition-colors duration-300"
          @click="$emit('close')"
        >
          HOME
        </router-link>
        <router-link
          to="/about"
          class="hover:text-zinc-300 transition-colors duration-300"
          @click="$emit('close')"
        >
          ABOUT
        </router-link>
        <router-link
          to="/work"
          class="hover:text-zinc-300 transition-colors duration-300"
          @click="$emit('close')"
        >
          WORK
        </router-link>
        <router-link
          to="/contact"
          class="hover:text-zinc-300 transition-colors duration-300"
          @click="$emit('close')"
        >
          CONTACT
        </router-link>
      </nav>
    </div>
  </div>
</template>

<script setup>
import LogoIcon from '@/components/icons/LogoIcon.vue'

defineProps({
  isOpen: {
    type: Boolean,
    default: false
  }
})

defineEmits(['close'])
</script>

<style scoped>
.router-link-active {
  @apply text-zinc-700;
}
</style>
