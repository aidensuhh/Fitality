<script setup>
import fitalityLogo from '../assets/Fitality.jpg'
</script>

<template>
  <nav class="fixed w-full px-6 py-4 bg-purple-900/50 backdrop-blur-lg z-50">
    <div class="container mx-auto flex justify-between items-center">
      <div class="flex items-center gap-3">
        <div class="w-12 h-12 flex items-center justify-center bg-white/10 rounded-full p-1 border border-purple-400/20 backdrop-blur-sm hover:bg-white/15 transition-colors">
          <img 
            :src="fitalityLogo"
            alt="Fitality" 
            class="w-full h-full object-contain rounded-full"
          />
        </div>
        <span class="text-2xl font-bold bg-gradient-to-r from-cyan-400 to-purple-400 bg-clip-text text-transparent">Fitality</span>
      </div>
      <div class="flex items-center gap-6">
        <button class="text-purple-200 hover:text-white transition-colors">Features</button>
        <button class="text-purple-200 hover:text-white transition-colors">About</button>
        <button class="text-purple-200 hover:text-white transition-colors">Contact</button>
        <button class="px-6 py-2 bg-white/10 rounded-lg hover:bg-white/20 transition-colors">
          Login
        </button>
      </div>
    </div>
  </nav>
</template>

<style scoped>
.nav-button {
  @apply px-4 py-2 text-gray-300 hover:text-white transition-colors;
}
</style> 