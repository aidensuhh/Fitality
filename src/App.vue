<script setup>
import { animate, stagger, spring } from 'motion'
import { onMounted } from 'vue'
import TheNavbar from './components/TheNavbar.vue'
import StatCard from './components/StatCard.vue'
import PixelCharacter from './components/PixelCharacter.vue'
import PixelEffects from './components/PixelEffects.vue'

onMounted(() => {
  // Initial screen flash
  animate('.screen-flash', {
    opacity: [1, 0],
  }, {
    duration: 0.5,
  })

  // Title entrance with glitch effect
  animate('.game-title', [
    { scale: [1.2, 1], x: [-10, 0], opacity: [0, 1] },
    { x: [0, 2, -2, 0], duration: 0.2, delay: 0.5 },
  ], {
    duration: 0.8,
    easing: spring({ stiffness: 100 })
  })

  // Characters staggered entrance
  animate('.character-entrance', {
    opacity: [0, 1],
    x: [-100, 0],
    scale: [0.8, 1],
  }, {
    delay: stagger(0.2, { start: 0.5 }),
    duration: 0.5,
    easing: spring({ stiffness: 200 })
  })

  // Stats cards with pixel spread
  animate('.stat-card', {
    opacity: [0, 1],
    scale: [0.8, 1],
    y: [20, 0],
  }, {
    delay: stagger(0.1, { start: 0.8 }),
    duration: 0.5,
    easing: spring({ stiffness: 200 })
  })

  // Form entrance
  animate('.game-menu', {
    opacity: [0, 1],
    x: [50, 0],
  }, {
    delay: 1,
    duration: 0.5,
  })
})
</script>

<template>
  <div class="min-h-screen bg-gradient-to-br from-purple-700 via-purple-800 to-purple-900 text-white overflow-hidden">
    <!-- Screen flash effect -->
    <div class="screen-flash fixed inset-0 bg-white pointer-events-none"></div>
    
    <!-- Background effects -->
    <PixelEffects />

    <TheNavbar />
    
    <main class="container mx-auto px-4 pt-20 lg:pt-32 pb-20 flex min-h-screen items-center relative">
      <!-- Pixel art decorations -->
      <div class="absolute inset-0 pointer-events-none">
        <!-- Scanlines effect -->
        <div class="absolute inset-0 bg-scanlines opacity-[0.03]"></div>
        
        <!-- Pixel corners -->
        <div class="absolute top-10 left-10 pixel-corner"></div>
        <div class="absolute top-10 right-10 pixel-corner transform rotate-90"></div>
        <div class="absolute bottom-10 left-10 pixel-corner transform -rotate-90"></div>
        <div class="absolute bottom-10 right-10 pixel-corner transform rotate-180"></div>
      </div>

      <!-- Character decorations with enhanced positioning -->
      <div class="absolute left-0 bottom-0 character-entrance transform hover:scale-110 transition-transform">
        <PixelCharacter type="wizard" />
      </div>
      <div class="absolute right-0 bottom-0 character-entrance transform hover:scale-110 transition-transform">
        <PixelCharacter type="merchant" />
      </div>
      <div class="absolute left-1/4 bottom-20 character-entrance transform hover:scale-110 transition-transform">
        <PixelCharacter type="warrior" />
      </div>

      <div class="grid lg:grid-cols-2 gap-12 items-center w-full max-w-6xl mx-auto">
        <!-- Left Column -->
        <div class="space-y-8 relative mx-auto w-full max-w-2xl">
          <!-- Decorative pixels -->
          <div class="absolute -top-10 -left-10 w-20 h-20 bg-purple-500/20 rounded-lg rotate-12"></div>
          <div class="absolute -bottom-10 -right-10 w-16 h-16 bg-cyan-500/20 rounded-lg -rotate-12"></div>

          <div class="game-title relative z-10">
            <h1 class="text-4xl md:text-5xl lg:text-7xl font-bold leading-[1.15] tracking-tight -mt-12 text-center">
              Level Up Your
              <div class="mt-4 md:mt-5 mb-6 flex flex-col items-center space-y-0">
                <div class="relative inline-block">
                  <span class="text-transparent bg-clip-text bg-gradient-to-r from-cyan-400 via-purple-400 to-cyan-400 inline-block transform hover:scale-105 transition-transform cursor-pointer">
                    Financial 
                  </span>
                </div>
                <div class="relative inline-block overflow-visible -mt-1">
                  <span 
                    class="text-transparent bg-clip-text bg-gradient-to-r from-purple-400 via-cyan-400 to-purple-400 inline-block transform hover:scale-105 transition-transform cursor-pointer"
                    style="line-height: 1.3;"
                  >
                    Journey
                  </span>
                </div>
              </div>
            </h1>
            
            <div class="mt-4 md:mt-6 relative flex flex-col items-center text-center">
              <div class="pb-4">
                <p class="text-lg md:text-xl text-purple-200 font-medium tracking-wide">
                  Join the quest for financial mastery!
                </p>
                <p class="mt-2 text-sm md:text-base text-purple-300/80">
                  Press START to begin your adventure
                </p>
              </div>
            </div>
          </div>

          <!-- Stats cards with pixel art style -->
          <div class="grid grid-cols-3 gap-4 max-w-xl mx-auto">
            <StatCard value="100+" label="Quests" valueColor="text-cyan-400" class="stat-card" />
            <StatCard value="50+" label="Skills" valueColor="text-purple-400" class="stat-card" />
            <StatCard value="15+" label="Metrics Tracked" valueColor="text-pink-400" class="stat-card" />
          </div>
        </div>

        <!-- Right Column - Game Menu Style Form -->
        <div class="relative mx-auto w-full max-w-md">
          <div class="absolute inset-0 bg-gradient-to-r from-purple-500/10 to-cyan-500/10 rounded-2xl blur-xl"></div>
          <div class="relative bg-white/10 backdrop-blur-lg rounded-2xl p-8 border border-white/20">
            <h2 class="text-2xl font-bold mb-6">Start Your Journey</h2>
            <form class="space-y-4">
              <div>
                <input 
                  type="text" 
                  placeholder="Username"
                  class="w-full px-4 py-3 rounded-lg bg-white/5 border border-purple-400/30 focus:border-purple-400 focus:outline-none"
                />
              </div>
              <div>
                <input 
                  type="email" 
                  placeholder="Email"
                  class="w-full px-4 py-3 rounded-lg bg-white/5 border border-purple-400/30 focus:border-purple-400 focus:outline-none"
                />
              </div>
              <div>
                <input 
                  type="password" 
                  placeholder="Password"
                  class="w-full px-4 py-3 rounded-lg bg-white/5 border border-purple-400/30 focus:border-purple-400 focus:outline-none"
                />
              </div>
              <button class="w-full py-4 bg-gradient-to-r from-cyan-500 to-purple-500 rounded-lg font-semibold hover:opacity-90 transition-opacity">
                START
              </button>
              <div class="relative my-6">
                <div class="absolute inset-0 flex items-center">
                  <div class="w-full border-t border-purple-400/30"></div>
                </div>
                <div class="relative flex justify-center text-sm">
                  <span class="px-2 bg-purple-900 text-purple-200">Or continue with</span>
                </div>
              </div>
              <button class="w-full py-3 px-4 border border-purple-400/30 rounded-lg flex items-center justify-center gap-2 hover:bg-white/5 transition-colors">
                <img src="@/assets/google.svg" alt="Google" class="w-5 h-5" />
                Sign up with Google
              </button>
            </form>
          </div>
        </div>
      </div>
    </main>
  </div>
</template>

<style>
/* Pixel art styles */
.pixel-corner {
  width: 24px;
  height: 24px;
  background: 
    linear-gradient(45deg, transparent 0%, transparent 40%, theme('colors.purple.400' / 20%) 40%, theme('colors.purple.400' / 20%) 60%, transparent 60%, transparent 100%);
}

.bg-scanlines {
  background-image: linear-gradient(
    to bottom,
    transparent 50%,
    rgba(0, 0, 0, 0.5) 50%
  );
  background-size: 100% 4px;
  pointer-events: none;
}

/* Enhanced stat card styling */
.stat-card {
  @apply relative overflow-hidden;
  box-shadow: 0 0 0 2px theme('colors.purple.400' / 20%);
}

.stat-card::before {
  content: '';
  @apply absolute inset-0 bg-gradient-to-br from-white/5 to-transparent;
  mask-image: linear-gradient(45deg, #000 25%, transparent 25%),
              linear-gradient(-45deg, #000 25%, transparent 25%),
              linear-gradient(45deg, transparent 75%, #000 75%),
              linear-gradient(-45deg, transparent 75%, #000 75%);
  mask-size: 2px 2px;
}

/* Game menu hover effects */
.game-menu {
  @apply transition-transform duration-200;
}

.game-menu:hover {
  transform: translateY(-2px);
  box-shadow: 0 8px 32px rgba(0, 0, 0, 0.2);
}

/* Input field focus effects */
input:focus {
  @apply ring-2 ring-purple-400/50;
  animation: pulse 2s cubic-bezier(0.4, 0, 0.6, 1) infinite;
}

@keyframes pulse {
  0%, 100% { box-shadow: 0 0 0 0 theme('colors.purple.400' / 50%); }
  50% { box-shadow: 0 0 0 4px theme('colors.purple.400' / 25%); }
}
</style>
