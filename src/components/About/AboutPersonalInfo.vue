<template>
  <div class="w-full md:w-1/2 flex flex-col items-center gap-6">
    <div class="relative group md:block lg:block hidden">
      <img
        src="@/assets/img/langxmeng.jpg"
        alt="Profile picture"
        class="w-156 h-82 object-cover rounded-md border-4 border-lime-500 shadow-lg group-hover:scale-105 transition-transform duration-300"
      />
      <div
        class="absolute inset-0 rounded-full bg-lime-500 opacity-0 group-hover:opacity-10 transition-opacity duration-300"
      ></div>
    </div>
    <div
      class="bg-gray-800 rounded-xl p-8 w-full border border-lime-500 shadow-xl"
    >
      <h2 class="text-2xl text-lime-500 font-semibold mb-6">Personal Info</h2>
      <div class="space-y-4 text-gray-200">
        <div
          v-for="item in items"
          :key="item.label"
          class="flex items-center gap-4 transition-transform duration-200 hover:translate-x-2"
        >
          <span class="material-symbols-outlined text-lime-500 text-2xl">{{
            item.icon
          }}</span>
          <p class="text-lg">{{ item.label }}: {{ item.content }}</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from "vue";
const items = ref([
  { label: "Name", content: "Sreyvang PHON", icon: "person" },
  { label: "Email", content: "sreyvang@example.com", icon: "email" },
  { label: "Location", content: "Phnom Penh, Cambodia", icon: "location_on" },
  { label: "Profession", content: "Web Developer", icon: "work" },
]);
</script>

<style scoped>
.material-symbols-outlined {
  font-size: 24px;
  font-family: "Material Symbols Outlined", sans-serif;
}

@media (max-width: 768px) {
  img {
    width: 200px;
    height: 200px;
  }

  .p-8 {
    padding: 1.5rem;
  }
}

@media (max-width: 640px) {
  .text-lg {
    font-size: 1rem;
  }
}

.material-symbols-outlined {
  font-variation-settings: "FILL" 1, "wght" 400, "GRAD" 0, "opsz" 24;
}
</style>
