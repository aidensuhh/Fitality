<template>
  <div class="bg-white/5 backdrop-blur-sm rounded-xl p-4 text-center border border-purple-400/20">
    <div class="text-3xl font-bold" :class="valueColor">{{ value }}</div>
    <div class="text-sm text-purple-200">{{ label }}</div>
  </div>
</template>

<script setup>
defineProps({
  value: {
    type: String,
    required: true
  },
  label: {
    type: String,
    required: true
  },
  valueColor: {
    type: String,
    default: 'text-cyan-400'
  }
})
</script>

<style scoped>
.stat-card {
  @apply bg-white/5 backdrop-blur-sm rounded-xl p-4 text-center hover:bg-white/10 transition-colors;
}
</style> 