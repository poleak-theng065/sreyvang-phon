<template>
  <div
    class="flex flex-col rounded-lg overflow-hidden bg-black project-card"
    :class="{
      'animated-border': true,
      'md:flex-row': true,
      'md:flex-row-reverse': imagePosition === 'right'
    }"
  >
    <!-- Image Section -->
    <div class="relative w-full h-48 md:w-1/3 md:h-full">
      <img
        :src="project.imageUrl"
        :alt="`Project image for ${project.title}`"
        class="w-full h-full object-cover"
      />
      <!-- Tech Stack -->
      <TechStack :tech="project.tech" />
    </div>

    <!-- Info Section -->
    <div class="w-full md:w-2/3 bg-black p-4 md:p-6 flex flex-col justify-between gap-4 h-full relative">
      <div>
        <h2 class="text-xl md:text-2xl font-semibold mb-2 md:mb-3 text-lime-500">{{ project.title }}</h2>
        <p class="text-gray-300 mb-2 md:mb-3 text-sm md:text-base">{{ project.description }}</p>
        <div class="extra-details">
          <div v-for="(detail, index) in sanitizedDetails" :key="index">
            <p class="text-xs md:text-sm text-lime-100" v-html="detail"></p>
          </div>
        </div>
      </div>

      <!-- Footer with profile and links -->
      <div class="relative h-16 md:h-14 flex flex-col md:flex-row items-start md:items-center justify-between mt-3 md:mt-4">
        <div class="flex items-center space-x-2 md:space-x-3 relative w-full md:w-2/3 h-12 md:h-14 mb-2 md:mb-0">
          <div
            v-for="(member, index) in project.team"
            :key="member.name"
            class="profile flex items-center gap-4 space-x-2 md:space-x-3 absolute inset-0"
            :class="{
              'opacity-100 z-10 translate-y-0': currentProfileIndex === index,
              'opacity-0 -z-10 translate-y-2': currentProfileIndex !== index
            }"
          >
            <img
              :alt="`Avatar of ${member.name}`"
              class="w-12 h-12 rounded-full object-cover border border-lime-500"
              :src="member.avatar"
            />
            <div>
              <p class="font-semibold text-sm text-white">{{ member.name }}</p>
              <p class="text-xs text-lime-500">{{ member.role }}</p>
            </div>
          </div>
        </div>

        <!-- Links -->
        <div class="flex space-x-4 text-lime-500 text-2xl self-end md:self-auto">
          <a
            v-for="link in project.links"
            :key="link.icon"
            :aria-label="`${link.icon.includes('github') ? 'GitHub' : 'Website'} link`"
            class="icon-link hover:text-lime-300"
            :href="link.url"
            target="_blank"
            rel="noopener noreferrer"
          >
            <i :class="link.icon"></i>
          </a>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref, computed, onMounted, onUnmounted, watch } from "vue";
import TechStack from "@/components/Project/TechStack.vue";

const props = defineProps({
  project: {
    type: Object,
    required: true,
    validator: (value) => {
      return (
        value &&
        typeof value === "object" &&
        "title" in value &&
        "description" in value &&
        "imageUrl" in value &&
        Array.isArray(value.tech) &&
        Array.isArray(value.team) &&
        Array.isArray(value.links) &&
        Array.isArray(value.details)
      );
    },
  },
  imagePosition: {
    type: String,
    default: "left",
    validator: (value) => ["left", "right"].includes(value),
  },
});

const emit = defineEmits(["rotate-profile"]);

const currentProfileIndex = ref(0);
let intervalId = null;

const sanitizedDetails = computed(() => {
  return props.project.details.map((detail) =>
    detail.replace(/<strong>(.*?)<\/strong>/g, '<span class="font-bold">$1</span>')
  );
});

const startRotation = () => {
  clearInterval(intervalId);
  currentProfileIndex.value = 0;

  intervalId = setInterval(() => {
    currentProfileIndex.value = (currentProfileIndex.value + 1) % props.project.team.length;
    emit("rotate-profile", props.project.id);
  }, 7000);
};

onMounted(() => {
  startRotation();
});

onUnmounted(() => {
  clearInterval(intervalId);
});

watch(
  () => props.project,
  () => {
    startRotation();
  },
  { deep: true }
);
</script>

<style scoped>
.animated-border {
  animation: borderGlow 4s ease-in-out infinite;
  border: 2px solid;
}

.project-card {
  transition: height 0.5s ease, box-shadow 0.3s ease;
  height: auto;
  min-height: 18rem;
  overflow: hidden;
  position: relative;
  width: 100%;
  max-width: 1200px;
  margin: 0 auto;
}

@media (min-width: 768px) {
  .project-card {
    height: 18rem;
  }
  .project-card:hover {
    height: 24rem;
  }
}

.project-card:hover {
  box-shadow: 0 0 30px #bef264;
  z-index: 10;
}

.extra-details {
  max-height: 0;
  opacity: 0;
  transition: max-height 0.5s ease, opacity 0.5s ease;
  overflow: hidden;
  color: #d9f99d;
  font-size: 0.75rem;
  margin-top: 0.5rem;
}

@media (min-width: 768px) {
  .extra-details {
    font-size: 0.875rem;
  }
  .project-card:hover .extra-details {
    max-height: 12rem;
    opacity: 1;
  }
}

.profile {
  transition: opacity 0.5s ease, transform 0.5s ease;
}

.icon-link:hover {
  color: #bef264;
}

@keyframes borderGlow {
  0%,
  100% {
    border-color: #84cc16;
    box-shadow: 0 0 8px #84cc16;
  }
  50% {
    border-color: #bef264;
    box-shadow: 0 0 20px #bef264;
  }
}
</style>