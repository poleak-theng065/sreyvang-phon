<template>
  <div id="highlight" class="flex w-full py-4 gap-6 overflow-hidden">
    <div class="flex animate-marquee gap-24">
      <div
        v-for="item in items"
        :key="item.name"
        class="mx-4 flex gap-2 items-center"
      >
        <img :src="item.img" :alt="item.name" class="w-12 h-12 object-contain mb-2" />
        <h2 class="text-white font-semibold">{{ item.name }}</h2>
      </div>
      <!-- Duplicate items for seamless looping -->
      <div
        v-for="item in items"
        :key="item.name + '-duplicate'"
        class="mx-4 flex gap-2 items-center"
      >
        <img :src="item.img" :alt="item.name" class="w-12 h-12 object-contain mb-2" />
        <h2 class="text-white font-semibold">{{ item.name }}</h2>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue'

const items = ref([
  { name: 'Figma', img: '../../src/assets/img/icon/figma.png' },
  { name: 'Jira', img: '../../src/assets/img/icon/jira.png' },
  { name: 'GitHub', img: '../../src/assets/img/icon/github.png' },
  { name: 'Notion', img: '../../src/assets/img/icon/notion.png' },
  { name: 'Vue.js', img: '../../src/assets/img/icon/vue.png' },
  { name: 'Node.js', img: '../../src/assets/img/icon/node.png' },
  { name: 'Tailwind CSS', img: '../../src/assets/img/icon/tailwind.png' },
  { name: 'HTML5', img: '../../src/assets/img/icon/html5.png' },
  { name: 'CSS', img: '../../src/assets/img/icon/css.webp' },
  { name: 'JavaScript', img: '../../src/assets/img/icon/javascript.png' },
  { name: 'Sass', img: '../../src/assets/img/icon/sass.png' },
  { name: 'Bootstrap', img: '../../src/assets/img/icon/bootstrap.svg' },
  { name: 'PHP', img: '../../src/assets/img/icon/php.svg' },
  { name: 'Laravel', img: '../../src/assets/img/icon/laravel.png' }
])


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