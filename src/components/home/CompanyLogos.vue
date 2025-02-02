<template>
  <div class="flex whitespace-nowrap animate-marquee">
    <div class="flex gap-16 items-center">
      <span
        class="text-lg md:text-xl font-medium opacity-50 hover:opacity-100 transition-opacity uppercase tracking-wider"
        >Альмапарк</span
      >
      <span
        class="text-lg md:text-xl font-medium opacity-50 hover:opacity-100 transition-opacity uppercase tracking-wider"
        >Росбанк</span
      >
      <span
        class="text-lg md:text-xl font-medium opacity-50 hover:opacity-100 transition-opacity uppercase tracking-wider"
        >Альмапарк</span
      >
      <span
        class="text-lg md:text-xl font-medium opacity-50 hover:opacity-100 transition-opacity uppercase tracking-wider"
        >Росбанк</span
      >
      <span
        class="text-lg md:text-xl font-medium opacity-50 hover:opacity-100 transition-opacity uppercase tracking-wider"
        >Альмапарк</span
      >
      <span
        class="text-lg md:text-xl font-medium opacity-50 hover:opacity-100 transition-opacity uppercase tracking-wider"
        >Росбанк</span
      >
    </div>
    <div class="flex gap-32 items-center">
      <span
        class="text-lg md:text-xl font-medium opacity-50 hover:opacity-100 transition-opacity uppercase tracking-wider"
        >Альмапарк</span
      >
      <span
        class="text-lg md:text-xl font-medium opacity-50 hover:opacity-100 transition-opacity uppercase tracking-wider"
        >Росбанк</span
      >
      <span
        class="text-lg md:text-xl font-medium opacity-50 hover:opacity-100 transition-opacity uppercase tracking-wider"
        >Альмапарк</span
      >
      <span
        class="text-lg md:text-xl font-medium opacity-50 hover:opacity-100 transition-opacity uppercase tracking-wider"
        >Росбанк</span
      >
      <span
        class="text-lg md:text-xl font-medium opacity-50 hover:opacity-100 transition-opacity uppercase tracking-wider"
        >Альмапарк</span
      >
      <span
        class="text-lg md:text-xl font-medium opacity-50 hover:opacity-100 transition-opacity uppercase tracking-wider"
        >Росбанк</span
      >
    </div>
  </div>
</template>

<style scoped>
.animate-marquee {
  animation: marquee 20s linear infinite;
}

@keyframes marquee {
  0% {
    transform: translateX(100vw);
  }
  100% {
    transform: translateX(-100%);
  }
}
</style>
