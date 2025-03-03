<script setup>
import { motion } from '@vueuse/motion'  // Changed from MotionDiv
</script>

<template>
  <motion.div
    :initial="{ opacity: 0, scale: 0.9 }"
    :animate="{ opacity: 1, scale: 1 }"
    :transition="{ duration: 0.5 }"
    class="relative group"
  >
    <div class="game-card">
      <div class="absolute inset-0 bg-gradient-to-r from-purple-500/10 to-pink-500/10 group-hover:from-purple-500/20 group-hover:to-pink-500/20 transition-all duration-300 rounded-xl"></div>
      <slot></slot>
    </div>
  </motion.div>
</template>

<style scoped>
.game-card {
  @apply relative p-6 rounded-xl border border-white/10 backdrop-blur-sm;
}
</style> 