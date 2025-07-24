<template>
  <div class="bg-gray-800/70 backdrop-blur-sm p-8 rounded-2xl border border-lime-500/20 shadow-lg hover:shadow-lime-500/10 transition-all flex flex-col gap-2">
    <h3 class="text-2xl font-bold mb-6 flex items-center">
      <span class="bg-gradient-to-r from-lime-400 to-lime-600 bg-clip-text text-transparent">
        Technical Expertise
      </span>
    </h3>
    <div class="space-y-5 flex flex-col gap-2">
      <div v-for="skill in skills" :key="skill.name" class="group">
        <div class="flex justify-between items-center mb-1 min-h-8">
          <div class="flex gap-2 pl-1">
            <img :src="skill.icon" :alt="skill.name" :class="skill.size" class="object-contain" />
            <span class="font-medium text-gray-300 group-hover:text-lime-300 transition-colors">
              {{ skill.name }}
            </span>
          </div>
          <span class="text-sm font-mono text-lime-400">
            {{ animatedLevels[skill.name] || 0 }}%
          </span>
        </div>
        <div class="w-full bg-gray-700 h-3 rounded-full overflow-hidden">
          <div
            :style="{ width: (animatedLevels[skill.name] || 0) + '%' }"
            class="h-full bg-gradient-to-r from-lime-500 to-lime-300 rounded-full transition-all duration-1000 ease-out"
            :class="{ 'animate-pulse': skill.level > 90 }"
          ></div>
        </div>
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