<template>
  <div class="flex flex-col items-center justify-center gap-12 py-8 px-4 md:px-16 bg-black min-h-screen" id="about">
    <h1 class="text-4xl md:text-5xl text-lime-500 font-bold text-center mb-12 animate-fade-in">
      About Me
    </h1>
    <div class="flex flex-col md:flex-row items-center justify-center gap-8 w-full max-w-7xl">
      <AboutTextContent />
      <AboutPersonalInfo />
    </div>
  </div>
</template>

<script setup>
import AboutTextContent from '@/components/About/AboutTextContent.vue';
import AboutPersonalInfo from '@/components/About/AboutPersonalInfo.vue';
</script>

<style scoped>
@keyframes fade-in {
  from {
    opacity: 0;
    transform: translateY(20px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

.animate-fade-in {
  animation: fade-in 1s ease-out forwards;
}

@media (max-width: 768px) {
  .text-4xl {
    font-size: 2.25rem;
  }
}

@media (max-width: 640px) {
  .max-w-7xl {
    max-width: 100%;
  }
}
</style>