<script setup>
defineProps({
  label: String,
  number: Number,
})
</script>
<template>
  <div class="segment text-center">
    <div class="pt-10 overflow-hidden relative">
      <transition name="slide-up">

        <span :key="number" class="numbers text-green absolute top-0 left-[50%]">{{ number }}</span>
      </transition>
    </div>

    <span class="label block pt-2">{{ label }}</span>
  </div>
</template>
<style>
.segment {
  width: 80px;
}

.numbers {
  transform: translateX(-50%);
  font-size: 32px;
}

.label {
  font-size: 16px;
}

.slide-up-enter-active,
.slide-up-leave-active {
  transition: all 0.5s ease;
}

.slide-up-enter-from {
  opacity: 0;
  transform: translateX(-50%) translateY(100%);
}

.slide-up-leave-to {
  opacity: 0;
  transform: translate(-50%) translateY(-100%);
}
</style>
