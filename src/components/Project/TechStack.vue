<template>
  <div class="absolute bottom-2 right-2 md:bottom-3 md:right-3 bg-black bg-opacity-80 shadow-md rounded-md p-2 md:p-3 w-32 md:w-40 border border-lime-500">
    <h2 class="font-semibold mb-1 md:mb-2 text-sm md:text-base text-lime-500">Tech</h2>
    <ul class="space-y-1 text-xs md:text-sm text-white">
      <li v-for="tech in tech" :key="tech.name" class="flex items-center gap-2">
        <img :alt="`${tech.name} logo`" class="w-3 h-3 md:w-4 md:h-4" :src="tech.icon" />
        <span>{{ tech.name }}</span>
      </li>
    </ul>
  </div>
</template>

<script setup>
defineProps({
  tech: {
    type: Array,
    required: true,
    validator: (value) =>
      Array.isArray(value) &&
      value.every((item) => "name" in item && "icon" in item),
  },
});
</script>