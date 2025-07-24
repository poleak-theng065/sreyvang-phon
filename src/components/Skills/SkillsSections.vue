<template>
  <div class="w-full lg:w-2/3 max-w-2xl space-y-8 flex flex-col gap-4">
    <HardSkills :skills="hardSkills" :animatedLevels="animatedLevels" />
    <SoftSkills :skills="softSkills" :animatedLevels="animatedLevels" />
  </div>
</template>

<script setup>
import { ref, onMounted } from "vue";
import HardSkills from "./HardSkills.vue";
import SoftSkills from "./SoftSkills.vue";

// Import all icons
import tailwindIcon from "@/assets/img/icon/tailwind.png";
import bootstrapIcon from "@/assets/img/icon/bootstrap.svg";
import javascriptIcon from "@/assets/img/icon/javascript.png";
import phpIcon from "@/assets/img/icon/php.svg";
import nodeIcon from "@/assets/img/icon/node.png";
import vueIcon from "@/assets/img/icon/vue.png";
import laravelIcon from "@/assets/img/icon/laravel.png";
import githubIcon from "@/assets/img/icon/github.png";

const hardSkills = ref([
  {
    name: "Tailwind",
    level: 72,
    icon: tailwindIcon,
    size: "w-6.5 h-4.5",
  },
  {
    name: "Boostrap",
    level: 62,
    icon: bootstrapIcon,
    size: "w-6.6 h-5",
  },
  {
    name: "JavaScript",
    level: 92,
    icon: javascriptIcon,
    size: "w-5 h-5",
  },
  {
    name: "PHP/MVC",
    level: 88,
    icon: phpIcon,
    size: "w-7 h-5",
  },
  {
    name: "Node.JS/Express",
    level: 85,
    icon: nodeIcon,
    size: "w-5 h-6",
  },
  {
    name: "Vue.JS",
    level: 95,
    icon: vueIcon,
    size: "w-5 h-5",
  },
  {
    name: "Laravel",
    level: 83,
    icon: laravelIcon,
    size: "w-5 h-5",
  },
  {
    name: "Git/GitHub",
    level: 78,
    icon: githubIcon,
    size: "w-6 h-6",
  },
]);

const softSkills = ref([
  { name: "Khmer", level: 100 },
  { name: "English", level: 80 },
  { name: "Thai", level: 60 },
  { name: "Communication", level: 70 },
  { name: "Team Leadership", level: 85 },
  { name: "Problem Solving", level: 88 },
  { name: "Time Management", level: 82 },
  { name: "Adaptability", level: 87 },
  { name: "Creativity", level: 80 },
]);

const animatedLevels = ref({});

const animateValues = () => {
  const allSkills = [...hardSkills.value, ...softSkills.value];

  allSkills.forEach((skill) => {
    let start = 0;
    const end = skill.level;
    const duration = 1500;
    const incrementTime = duration / end;

    const timer = setInterval(() => {
      start += 1;
      animatedLevels.value[skill.name] = start;

      if (start >= end) {
        clearInterval(timer);
      }
    }, incrementTime);
  });
};

onMounted(() => {
  setTimeout(animateValues, 300);
});
</script>