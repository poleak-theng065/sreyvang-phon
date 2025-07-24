<template>
  <a
    :href="item.path"
    class="flex gap-1 items-center text-lg sm:text-xl md:text-2xl text-lime-500 cursor-pointer transition-transform duration-300 hover:-translate-y-2 relative group"
  >
    <span
      class="absolute left-0 -bottom-1 w-full h-0.5 bg-lime-500 scale-x-0 group-hover:scale-x-100 transition-transform duration-300 origin-left"
    ></span>
    <span class="material-symbols-outlined text-base sm:text-lg md:text-2xl"> {{ item.icon }} </span>
    <h2 class="text-base sm:text-lg md:text-xl">{{ item.label }}</h2>
  </a>
</template>

<script setup>
defineProps(["item"]);
</script>

<style scoped>
h2 {
  font-family: "Poppins", sans-serif;
}
</style>
