<template>
  <div class="w-full lg:w-1/3 max-w-xl relative overflow-hidden rounded-2xl border-2 border-lime-500/30 shadow-lg hover:shadow-lime-500/20 transition-all duration-300">
    <img
      src="@/assets/img/lang.jpg"
      alt="Profile"
      class="w-full h-full object-cover object-top animate-fade-in"
    />
    <div class="absolute inset-0 bg-gradient-to-t from-black/70 to-transparent"></div>
    <div class="absolute bottom-0 left-0 right-0 p-6 text-center">
      <div class="inline-flex items-center px-4 py-2 bg-lime-500/90 rounded-full">
        <svg
          class="w-5 h-5 mr-2 animate-pulse"
          fill="none"
          stroke="currentColor"
          viewBox="0 0 24 24"
        >
          <path
            stroke-linecap="round"
            stroke-linejoin="round"
            stroke-width="2"
            d="M13 10V3L4 14h7v7l9-11h-7z"
          ></path>
        </svg>
        <span class="font-medium">Available for work</span>
      </div>
    </div>
  </div>
</template>

<script setup>
// No logic needed for this component
</script>

<style scoped>
.animate-fade-in {
  animation: fadeIn 1.5s ease-in-out;
}

@keyframes fadeIn {
  from {
    opacity: 0;
    transform: scale(1.05);
  }
  to {
    opacity: 1;
    transform: scale(1);
  }
}
</style>