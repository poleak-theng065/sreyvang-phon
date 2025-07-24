<template>
  <div class="flex flex-col gap-4 space-y-12 lg:space-y-12">
    <h2
      class="text-2xl md:text-3xl lg:text-4xl font-medium tracking-wide text-gray-300 animate-fade-in-down"
    >
      Hi! My Name is
    </h2>
    <h1
      class="text-5xl md:text-6xl lg:text-6xl font-extrabold text-transparent bg-clip-text bg-gradient-to-r from-lime-400 via-lime-500 to-green-400 leading-tight drop-shadow-lg animate-fade-in-down delay-100 name-letter-spacing"
      style="word-spacing: 0.5em"
    >
      Sreyvang PHON
    </h1>
    <!-- Digital Details -->
    <div
      class="text-gray-400 space-y-1 text-sm md:text-base max-w-xs animate-fade-in-down delay-200 flex flex-col gap-2"
    >
      <p class="flex items-center gap-2">
        <span class="material-symbols-outlined text-lime-500"> mobile_3 </span>
        +855 12 345 678
      </p>
      <p class="flex items-center gap-2">
        <span class="material-symbols-outlined text-lime-500"> mail </span>
        sreyvang.phon@example.com
      </p>
      <p class="flex items-center gap-2">
        <span class="material-symbols-outlined text-lime-500">
          explore_nearby
        </span>
        SenSok, Phnom Penh, Cambodia
      </p>
    </div>
    <div class="flex space-x-4 md:space-x-6 gap-4">
      <div
        class="bg-gradient-to-br from-gray-900 to-gray-800 p-5 w-24 h-24 md:w-28 md:h-28 flex flex-col items-center justify-center border border-gray-800 rounded-2xl shadow-xl hover:scale-105 transition-transform duration-300"
      >
        <span class="text-lg md:text-xl font-medium text-gray-400"> XP </span>
        <span
          class="text-2xl md:text-3xl font-extrabold text-lime-400 mt-1 no-bounce"
        >
          0
        </span>
      </div>
      <div
        class="bg-gradient-to-br from-gray-900 to-gray-800 p-5 w-24 h-24 md:w-28 md:h-28 flex flex-col items-center justify-center border border-gray-800 rounded-2xl shadow-xl hover:scale-105 transition-transform duration-300"
      >
        <span class="text-lg md:text-xl font-medium text-gray-400">
          Projects
        </span>
        <span
          class="text-2xl md:text-3xl font-extrabold text-lime-400 mt-1 no-bounce"
        >
          10
        </span>
      </div>
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style scoped>
@keyframes fade-in-down {
  0% {
    opacity: 0;
    transform: translateY(-30px);
  }
  100% {
    opacity: 1;
    transform: translateY(0);
  }
}
</style>