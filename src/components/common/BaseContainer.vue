<template>
  <div :class="containerClasses">
    <slot />
  </div>
</template>

<script setup>
import { computed } from 'vue'

const props = defineProps({
  size: {
    type: String,
    default: 'default',
    validator: (value) => ['sm', 'md', 'lg', 'xl', 'full', 'default'].includes(value),
  },
  padding: {
    type: String,
    default: 'default',
    validator: (value) => ['none', 'sm', 'md', 'lg', 'xl', 'default'].includes(value),
  },
  center: {
    type: Boolean,
    default: true,
  },
})

const containerClasses = computed(() => {
  const classes = ['container-base']

  // Размер контейнера
  switch (props.size) {
    case 'sm':
      classes.push('container-sm')
      break
    case 'md':
      classes.push('container-md')
      break
    case 'lg':
      classes.push('container-lg')
      break
    case 'xl':
      classes.push('container-xl')
      break
    case 'full':
      classes.push('container-full')
      break
    default:
      classes.push('container-default')
  }

  // Отступы
  switch (props.padding) {
    case 'none':
      classes.push('padding-none')
      break
    case 'sm':
      classes.push('padding-sm')
      break
    case 'md':
      classes.push('padding-md')
      break
    case 'lg':
      classes.push('padding-lg')
      break
    case 'xl':
      classes.push('padding-xl')
      break
    default:
      classes.push('padding-default')
  }

  // Центрирование
  if (props.center) {
    classes.push('container-center')
  }

  return classes
})
</script>

<style scoped>
.container-base {
  width: 100%;
}

/* Размеры контейнеров */
.container-sm {
  max-width: var(--container-sm);
}

.container-md {
  max-width: var(--container-md);
}

.container-lg {
  max-width: var(--container-lg);
}

.container-xl {
  max-width: var(--container-xl);
}

.container-default {
  max-width: var(--container-max);
}

.container-full {
  max-width: none;
}

/* Центрирование */
.container-center {
  margin-left: auto;
  margin-right: auto;
}

/* Отступы */
.padding-none {
  padding: 0;
}

.padding-sm {
  padding-left: var(--spacing-md);
  padding-right: var(--spacing-md);
}

.padding-md {
  padding-left: var(--spacing-lg);
  padding-right: var(--spacing-lg);
}

.padding-lg {
  padding-left: var(--spacing-xl);
  padding-right: var(--spacing-xl);
}

.padding-xl {
  padding-left: var(--spacing-2xl);
  padding-right: var(--spacing-2xl);
}

.padding-default {
  padding-left: var(--page-padding-mobile);
  padding-right: var(--page-padding-mobile);
}

@media (min-width: 768px) {
  .padding-default {
    padding-left: var(--page-padding-tablet);
    padding-right: var(--page-padding-tablet);
  }

  .padding-sm {
    padding-left: var(--page-padding-tablet);
    padding-right: var(--page-padding-tablet);
  }
}

@media (min-width: 1024px) {
  .padding-default {
    padding-left: var(--page-padding-desktop);
    padding-right: var(--page-padding-desktop);
  }

  .padding-md {
    padding-left: var(--page-padding-desktop);
    padding-right: var(--page-padding-desktop);
  }

  .padding-lg {
    padding-left: var(--spacing-2xl);
    padding-right: var(--spacing-2xl);
  }
}
</style>
