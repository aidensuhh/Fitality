<template>
  <div class="pixel-effects">
    <!-- Floating pixels -->
    <div v-for="n in 20" :key="n" 
      class="pixel absolute w-2 h-2 bg-white/10"
      :style="{
        left: `${Math.random() * 100}%`,
        top: `${Math.random() * 100}%`,
        animationDelay: `${Math.random() * 2}s`
      }"
    ></div>

    <!-- Decorative corners -->
    <div class="absolute top-0 left-0 w-32 h-32 border-l-4 border-t-4 border-purple-400/20 rounded-tl-3xl"></div>
    <div class="absolute top-0 right-0 w-32 h-32 border-r-4 border-t-4 border-purple-400/20 rounded-tr-3xl"></div>
    <div class="absolute bottom-0 left-0 w-32 h-32 border-l-4 border-b-4 border-purple-400/20 rounded-bl-3xl"></div>
    <div class="absolute bottom-0 right-0 w-32 h-32 border-r-4 border-b-4 border-purple-400/20 rounded-br-3xl"></div>

    <!-- Pixel grid lines -->
    <div class="pixel-grid"></div>
  </div>
</template>

<style scoped>
.pixel-effects {
  @apply fixed inset-0 pointer-events-none overflow-hidden;
}

.pixel {
  image-rendering: pixelated;
  animation: float 3s ease-in-out infinite;
}

.pixel-grid {
  @apply absolute inset-0;
  background-size: 50px 50px;
  background-image: 
    linear-gradient(to right, theme('colors.purple.400' / 3%) 1px, transparent 1px),
    linear-gradient(to bottom, theme('colors.purple.400' / 3%) 1px, transparent 1px);
}

@keyframes float {
  0%, 100% { transform: translate(0, 0); }
  50% { transform: translate(10px, -10px); }
}

@media (prefers-reduced-motion: reduce) {
  .pixel { animation: none; }
}
</style> 