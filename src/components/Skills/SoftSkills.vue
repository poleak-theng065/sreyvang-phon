<template>
  <div class="bg-gray-800/70 backdrop-blur-sm p-8 rounded-2xl border border-lime-500/20 shadow-lg hover:shadow-lime-500/10 transition-all mt-4 flex flex-col gap-4">
    <h3 class="text-2xl font-bold mb-6 flex items-center">
      <span class="bg-gradient-to-r from-lime-400 to-lime-600 bg-clip-text text-transparent">
        Professional Skills
      </span>
    </h3>
    <div class="grid grid-cols-2 md:grid-cols-3 gap-6">
      <div v-for="skill in skills" :key="skill.name" class="text-center group">
        <div class="relative w-24 h-24 mx-auto mb-3">
          <svg class="w-full h-full transform rotate-90">
            <circle
              cx="50%"
              cy="50%"
              r="45%"
              fill="none"
              stroke="#1F2937"
              stroke-width="8"
              stroke-linecap="round"
            />
            <circle
              cx="50%"
              cy="50%"
              r="45%"
              fill="none"
              stroke="url(#limeGradient)"
              stroke-width="8"
              stroke-linecap="round"
              :stroke-dasharray="283"
              :stroke-dashoffset="283 - (283 * (animatedLevels[skill.name] || 0)) / 100"
              class="transition-all duration-1000 ease-out"
            />
          </svg>
          <svg width="0" height="0">
            <defs>
              <linearGradient id="limeGradient" x1="0%" y1="0%" x2="100%" y2="0%">
                <stop offset="0%" stop-color="#84cc16" />
                <stop offset="100%" stop-color="#65a30d" />
              </linearGradient>
            </defs>
          </svg>
          <span class="absolute top-1/2 left-1/2 transform -translate-x-1/2 -translate-y-1/2 text-xl font-bold bg-gradient-to-r from-lime-400 to-lime-600 bg-clip-text text-transparent">
            {{ animatedLevels[skill.name] || 0 }}%
          </span>
        </div>
        <p class="text-gray-300 group-hover:text-lime-300 transition-colors">
          {{ skill.name }}
        </p>
      </div>
    </div>
  </div>
</template>

<script setup>
defineProps({
  skills: {
    type: Array,
    required: true
  },
  animatedLevels: {
    type: Object,
    required: true
  }
});
</script>