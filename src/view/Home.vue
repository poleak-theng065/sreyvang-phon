<template>
  <div
    class="bg-black text-white min-h-screen flex flex-col items-center justify-center py-10 md:py-16 relative overflow-hidden"
    id="home"
  >
    <!-- Decorative Blobs -->
    <div
      class="absolute top-0 left-0 w-96 h-96 bg-lime-500 opacity-20 rounded-full blur-3xl -z-10 animate-pulse"
    ></div>
    <div
      class="absolute bottom-0 right-0 w-96 h-96 bg-blue-500 opacity-20 rounded-full blur-3xl -z-10 animate-pulse"
    ></div>
    <div class="container mx-auto px-6 max-w-7xl">
      <div class="grid grid-cols-1 lg:grid-cols-3 gap-6 xl:gap-10 items-center">
        <IntroColumn />
        <ImageColumn />
        <PositionColumn />
      </div>
    </div>
    <HightLight></HightLight>
  </div>
</template>

<script>
import IntroColumn from "@/components/Home/IntroColumn.vue";
import ImageColumn from "@/components/Home/ImageColumn.vue";
import PositionColumn from "@/components/Home/PositionColumn.vue";
import HightLight from "@/components/Home/HightLight.vue";

export default {
  components: {
    IntroColumn,
    ImageColumn,
    PositionColumn,
    HightLight,
  },
};
</script>

<style scoped>
html {
  scroll-behavior: smooth;
}
div {
  font-family: "Poppins", sans-serif;
}
</style>
