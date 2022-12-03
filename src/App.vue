<script setup>
import CountdownHeader from '@/components/CountdownHeader.vue'
import CountdownSegment from './components/CountdownSegment.vue'
import { useNow } from '@vueuse/core'
import { intervalToDuration } from 'date-fns'
import { computed } from 'vue';


const now = useNow()
const christmas = new Date('12/25/2022 00:00:00')
const intervalDuration = computed(() => intervalToDuration({ start: now.value, end: christmas }))
</script>
<template>
  <div class="w-full h-full flex justify-center items-center p-10">
    <div>
      <div class="shadow-md relative bg-white p-5 rounded-lg border-gray-100 border-[1px]">
        <CountdownHeader />
        <main class="flex justify-center">
          <CountdownSegment label="days" :number="intervalDuration.days" />
          <CountdownSegment label="hours" :number="intervalDuration.hours" />
          <CountdownSegment label="minutes" :number="intervalDuration.minutes" />
          <CountdownSegment label="seconds" :number="intervalDuration.seconds" />
        </main>
      </div>

      <h4 class="mt-10 text-gray-400 text-center text-sm">
        This challenge brought to you by <a href="https://vueschool.io/" class="underline">Vue School</a>
      </h4>
    </div>
  </div>
</template>

<style>
div {
  display: block;
}

body {
  @apply bg-gray-100;
}
</style>
