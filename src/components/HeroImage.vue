<template>
  <motion.div
    :initial="{ opacity: 0, x: 20 }"
    :animate="{ opacity: 1, x: 0 }"
    :transition="{ duration: 0.8, delay: 0.4 }"
    class="relative"
  >
    <div class="relative w-full h-[600px]">
      <div class="absolute inset-0 bg-gradient-to-r from-purple-500/20 to-pink-500/20 rounded-2xl backdrop-blur-sm"></div>
      <div 
        class="absolute inset-0 w-full h-full rounded-2xl bg-gradient-to-br from-purple-800/50 to-pink-800/50 flex items-center justify-center"
      >
        <span class="text-2xl text-white/50">Dashboard Preview</span>
      </div>
      <div class="absolute -top-4 -right-4 w-20 h-20 bg-purple-500/30 rounded-full blur-xl"></div>
      <div class="absolute -bottom-4 -left-4 w-20 h-20 bg-pink-500/30 rounded-full blur-xl"></div>
    </div>
  </motion.div>
</template>

<script setup>
import { motion } from '@vueuse/motion'
</script> 