<template>
  <div class="pixel-character" :class="type">
    <div class="character-container animate-float">
      <!-- Character base shape -->
      <div class="character">
        <div class="head"></div>
        <div class="body"></div>
        <div class="staff" v-if="type === 'wizard'"></div>
        <div class="sword" v-if="type === 'warrior'"></div>
        <div class="bag" v-if="type === 'merchant'"></div>
      </div>
      <!-- Floating coin -->
      <div class="coin animate-spin"></div>
    </div>
  </div>
</template>

<script setup>
defineProps({
  type: {
    type: String,
    default: 'wizard',
    validator: (value) => ['wizard', 'warrior', 'merchant'].includes(value)
  }
})
</script>

<style scoped>
.pixel-character {
  width: 48px;
  height: 48px;
  position: relative;
}

.character-container {
  position: relative;
  width: 100%;
  height: 100%;
}

.character {
  position: relative;
  width: 100%;
  height: 100%;
}

/* Base character shapes */
.head {
  width: 24px;
  height: 24px;
  background: #fff;
  position: absolute;
  top: 0;
  left: 50%;
  transform: translateX(-50%);
  border-radius: 4px;
  box-shadow: 0 0 0 2px rgba(0,0,0,0.2);
}

.body {
  width: 32px;
  height: 32px;
  background: currentColor;
  position: absolute;
  bottom: 0;
  left: 50%;
  transform: translateX(-50%);
  border-radius: 4px;
  box-shadow: 0 0 0 2px rgba(0,0,0,0.2);
}

/* Character types */
.wizard {
  color: #9333ea;
}

.warrior {
  color: #dc2626;
}

.merchant {
  color: #2563eb;
}

/* Accessories */
.staff {
  width: 4px;
  height: 40px;
  background: #92400e;
  position: absolute;
  bottom: 0;
  right: -8px;
  border-radius: 2px;
}

.sword {
  width: 6px;
  height: 32px;
  background: #94a3b8;
  position: absolute;
  bottom: 4px;
  right: -10px;
  transform: rotate(-45deg);
  border-radius: 2px;
}

.bag {
  width: 16px;
  height: 16px;
  background: #92400e;
  position: absolute;
  bottom: 8px;
  right: -12px;
  border-radius: 4px;
}

.coin {
  width: 12px;
  height: 12px;
  background: #fbbf24;
  position: absolute;
  top: -16px;
  right: -8px;
  border-radius: 50%;
  box-shadow: 0 0 0 2px rgba(0,0,0,0.2);
}

/* Animations */
@keyframes float {
  0%, 100% { transform: translateY(0); }
  50% { transform: translateY(-8px); }
}

@keyframes spin {
  0% { transform: scale(1); }
  50% { transform: scale(0.8); }
  100% { transform: scale(1); }
}

.animate-float {
  animation: float 2s ease-in-out infinite;
}

.animate-spin {
  animation: spin 1s ease-in-out infinite;
}
</style> 