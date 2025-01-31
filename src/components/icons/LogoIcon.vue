<template>
  <svg 
    viewBox="0 0 100 100" 
    xmlns="http://www.w3.org/2000/svg"
    :class="className"
  >
    <defs>
      <linearGradient id="logoGradient" x1="0%" y1="0%" x2="100%" y2="100%">
        <stop offset="0%" style="stop-color:#FF3B30;stop-opacity:1" />
        <stop offset="100%" style="stop-color:#FF4D42;stop-opacity:1" />
      </linearGradient>
    </defs>
    <circle 
      cx="50" 
      cy="50" 
      r="45" 
      :fill="color ? color : 'url(#logoGradient)'"
    />
    <path 
      d="M35 30v40h8V55h7l10 15h9L58 52c5-2 8-6 8-11 0-7-5-11-13-11H35zm8 6h10c4 0 6 2 6 5s-2 5-6 5H43V36z"
      fill="white"
    />
  </svg>
</template>

<script setup>
defineProps({
  className: {
    type: String,
    default: 'w-8 h-8'
  },
  color: {
    type: String,
    default: ''
  }
})
</script>
