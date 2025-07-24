<template>
  <div id="highlight" class="flex w-full py-4 gap-6 overflow-hidden">
    <div class="flex animate-marquee gap-24">
      <div
        v-for="item in items"
        :key="item.name"
        class="mx-4 flex gap-2 items-center"
      >
        <img :src="getImageUrl(item.img)" :alt="item.name" class="w-12 h-12 object-contain mb-2" />
        <h2 class="text-white font-semibold">{{ item.name }}</h2>
      </div>
      <!-- Duplicate items for seamless looping -->
      <div
        v-for="item in items"
        :key="item.name + '-duplicate'"
        class="mx-4 flex gap-2 items-center"
      >
        <img :src="getImageUrl(item.img)" :alt="item.name" class="w-12 h-12 object-contain mb-2" />
        <h2 class="text-white font-semibold">{{ item.name }}</h2>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue'

const items = ref([
  { name: 'Figma', img: 'figma.png' },
  { name: 'Jira', img: 'jira.png' },
  { name: 'GitHub', img: 'github.png' },
  { name: 'Notion', img: 'notion.png' },
  { name: 'Vue.js', img: 'vue.png' },
  { name: 'Node.js', img: 'node.png' },
  { name: 'Tailwind CSS', img: 'tailwind.png' },
  { name: 'HTML5', img: 'html5.png' },
  { name: 'CSS', img: 'css.webp' },
  { name: 'JavaScript', img: 'javascript.png' },
  { name: 'Sass', img: 'sass.png' },
  { name: 'Bootstrap', img: 'bootstrap.svg' },
  { name: 'PHP', img: 'php.svg' },
  { name: 'Laravel', img: 'laravel.png' }
])

// Helper function to construct proper image URLs
const getImageUrl = (name) => {
  return new URL(`/src/assets/img/icon/${name}`, import.meta.url).href
}
</script>

<style scoped>
.animate-marquee {
  display: flex;
  animation: marquee 50s linear infinite;
}

@keyframes marquee {
  0% {
    transform: translateX(0);
  }
  100% {
    transform: translateX(-50%);
  }
}

/* Ensure smooth transition by setting container width */
#highlight {
  position: relative;
  white-space: nowrap;
}
</style>