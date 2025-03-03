<template>
  <div class="space-y-8">
    <motion.div
      :initial="{ opacity: 0, y: 20 }"
      :animate="{ opacity: 1, y: 0 }"
      :transition="{ duration: 0.8 }"
    >
      <h1 class="text-5xl lg:text-7xl font-bold leading-tight">
        Level Up Your
        <span class="bg-gradient-to-r from-purple-400 to-pink-400 bg-clip-text text-transparent">
          Financial Game
        </span>
      </h1>
    </motion.div>

    <motion.div
      :initial="{ opacity: 0, y: 20 }"
      :animate="{ opacity: 1, y: 0 }"
      :transition="{ duration: 0.8, delay: 0.2 }"
      class="text-gray-300 text-lg"
    >
      Transform your financial journey into an epic adventure. Track, learn, and earn rewards while building your financial future.
    </motion.div>

    <motion.div
      :initial="{ opacity: 0, y: 20 }"
      :animate="{ opacity: 1, y: 0 }"
      :transition="{ duration: 0.8, delay: 0.4 }"
      class="grid grid-cols-3 gap-4"
    >
      <StatCard value="100" label="Max Score" valueColor="text-purple-400" />
      <StatCard value="50+" label="Achievements" valueColor="text-pink-400" />
      <StatCard value="24/7" label="AI Support" valueColor="text-blue-400" />
    </motion.div>

    <motion.div
      :initial="{ opacity: 0, scale: 0.9 }"
      :animate="{ opacity: 1, scale: 1 }"
      :transition="{ duration: 0.8, delay: 0.6 }"
    >
      <button class="px-8 py-4 bg-gradient-to-r from-purple-500 to-pink-500 rounded-full text-lg font-semibold hover:scale-105 transition-transform">
        Start Your Journey
      </button>
    </motion.div>
  </div>
</template>

<script setup>
import { motion } from '@vueuse/motion'
import StatCard from './StatCard.vue'
</script> 