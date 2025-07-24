<template>
  <div
    class="min-h-screen bg-black text-white flex flex-col items-center justify-center py-12"
    id="project"
  >
    <section class="w-full flex flex-col items-center justify-center gap-6">
      <h1
        class="text-4xl md:text-5xl text-lime-500 font-bold text-center mb-12 animate-fade-in"
      >
        My Projects
      </h1>

      <!-- Project Cards -->
      <ProjectCard
        v-for="(project, index) in projects"
        :key="project.id"
        :project="project"
        :image-position="index % 2 === 0 ? 'left' : 'right'"
        @rotate-profile="rotateProfile"
      />
    </section>
  </div>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from "vue";
import ProjectCard from "@/components/Project/ProjectCard.vue";

// Project data
const projects = ref([
  {
    id: 1,
    title: "POS Management System",
    description:
      "Led the development of a POS management system with real-time data updates and secure authentication. Designed system architecture and managed backend using Laravel. Ensured system stability through thorough testing and deployed on AWS for scalability.",
    imageUrl:
      "https://www.phoca.cz/images/phocacartproducts/templates/thumbs/phoca_thumb_l_pos.jpg",
    tech: [
      {
        name: "Laravel",
        icon: "https://upload.wikimedia.org/wikipedia/commons/thumb/9/9a/Laravel.svg/1969px-Laravel.svg.png",
      },
      {
        name: "PHP",
        icon: "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/php/php-original.svg",
      },
      {
        name: "MySQL",
        icon: "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/mysql/mysql-original.svg",
      },
    ],
    team: [
      {
        name: "Poleak Theng",
        role: "Scrum Master & Backend Developer",
        avatar: "https://randomuser.me/api/portraits/men/46.jpg",
      },
      {
        name: "Team Member A",
        role: "Frontend Developer",
        avatar: "https://randomuser.me/api/portraits/women/44.jpg",
      },
      {
        name: "Team Member B",
        role: "UI/UX Designer",
        avatar: "https://randomuser.me/api/portraits/women/65.jpg",
      },
    ],
    links: [
      { icon: "fab fa-github", url: "https://github.com" },
      { icon: "fas fa-globe", url: "https://example.com" },
    ],
    details: [
      "<strong>Features:</strong> Real-time data updates, secure authentication, AWS deployment.",
      "<strong>Technologies:</strong> Laravel, PHP, MySQL, phpMyAdmin.",
      "<strong>Outcome:</strong> Stable and scalable system with optimized database performance.",
    ],
  },
  {
    id: 2,
    title: "Quiz Web Application",
    description:
      "Designed and developed a responsive quiz application with real-time data handling. Integrated Firebase for database management and ensured a smooth user experience through thorough testing and debugging.",
    imageUrl:
      "https://storage.googleapis.com/a1aa/image/69ef1afa-a949-474d-1939-cea3c52f3ad7.jpg",
    tech: [
      {
        name: "JavaScript",
        icon: "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/javascript/javascript-original.svg",
      },
      {
        name: "Firebase",
        icon: "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/firebase/firebase-plain.svg",
      },
      {
        name: "HTML & CSS",
        icon: "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/html5/html5-original.svg",
      },
    ],
    team: [
      {
        name: "Poleak Theng",
        role: "Code Lead",
        avatar: "https://randomuser.me/api/portraits/men/46.jpg",
      },
      {
        name: "Team Member C",
        role: "Frontend Developer",
        avatar: "https://randomuser.me/api/portraits/women/33.jpg",
      },
      {
        name: "Team Member D",
        role: "Tester",
        avatar: "https://randomuser.me/api/portraits/men/60.jpg",
      },
    ],
    links: [
      { icon: "fab fa-github", url: "https://github.com" },
      { icon: "fas fa-globe", url: "https://example.com" },
    ],
    details: [
      "<strong>Features:</strong> Real-time quiz functionality, smooth user experience, responsive design.",
      "<strong>Technologies:</strong> JavaScript, Firebase, HTML, CSS.",
      "<strong>Outcome:</strong> Fully functional quiz application with database connectivity.",
    ],
  },
  {
    id: 3,
    title: "Face Detection System",
    description:
      "Developed a face detection system using Python for check-in/check-out tracking. Implemented facial recognition algorithms and led testing efforts to ensure accurate detection and system stability.",
    imageUrl:
      "https://developers.google.com/static/ml-kit/vision/face-detection/images/face_detection2x.png",
    tech: [
      {
        name: "Python",
        icon: "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/python/python-original.svg",
      },
      {
        name: "Tkinter",
        icon: "https://user-images.githubusercontent.com/42001064/120057695-b1f6c680-c062-11eb-96d5-2c43d05f9018.png",
      },
      {
        name: "NumPy",
        icon: "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/numpy/numpy-original.svg",
      },
    ],
    team: [
      {
        name: "Poleak Theng",
        role: "Team Leader",
        avatar: "https://randomuser.me/api/portraits/men/46.jpg",
      },
      {
        name: "Team Member E",
        role: "Developer",
        avatar: "https://randomuser.me/api/portraits/men/33.jpg",
      },
      {
        name: "Team Member F",
        role: "Tester",
        avatar: "https://randomuser.me/api/portraits/women/22.jpg",
      },
    ],
    links: [
      { icon: "fab fa-github", url: "https://github.com" },
      { icon: "fas fa-globe", url: "https://example.com" },
    ],
    details: [
      "<strong>Features:</strong> Real-time face detection, check-in/check-out tracking, accurate recognition.",
      "<strong>Technologies:</strong> Python, Tkinter, NumPy.",
      "<strong>Outcome:</strong> Functional face detection system with accurate performance.",
    ],
  },
  {
    id: 4,
    title: "Online Shop (Web Design)",
    description:
      "Contributed to the design and development of a fully responsive online shop. Designed website template in Figma and implemented using HTML and SASS with clean, maintainable code.",
    imageUrl:
      "https://blog-frontend.envato.com/cdn-cgi/image/width=1850,quality=75,format=auto/uploads/sites/2/2023/01/Screen-Shot-2023-01-16-at-2.12.40-pm.png",
    tech: [
      {
        name: "HTML",
        icon: "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/html5/html5-original.svg",
      },
      {
        name: "SASS",
        icon: "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/sass/sass-original.svg",
      },
      {
        name: "Figma",
        icon: "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/figma/figma-original.svg",
      },
    ],
    team: [
      {
        name: "Poleak Theng",
        role: "Developer & Designer",
        avatar: "https://randomuser.me/api/portraits/men/46.jpg",
      },
      {
        name: "Team Member G",
        role: "Team Member",
        avatar: "https://randomuser.me/api/portraits/women/44.jpg",
      },
      {
        name: "Team Member H",
        role: "Team Member",
        avatar: "https://randomuser.me/api/portraits/men/75.jpg",
      },
    ],
    links: [
      { icon: "fab fa-github", url: "https://github.com" },
      { icon: "fas fa-globe", url: "https://example.com" },
    ],
    details: [
      "<strong>Features:</strong> Fully responsive design, clean code, modern UI.",
      "<strong>Technologies:</strong> HTML, SASS, Figma.",
      "<strong>Outcome:</strong> Successfully deployed online shop compatible across devices.",
    ],
  },
]);

// Profile rotation intervals
const intervals = ref({});

const rotateProfile = (projectId) => {
  if (intervals.value[projectId]) {
    clearInterval(intervals.value[projectId]);
  }

  const project = projects.value.find((p) => p.id === projectId);
  if (!project) return;

  intervals.value[projectId] = setInterval(() => {
    // Emit event to child component to handle rotation
    const projectCard = projects.value.find((p) => p.id === projectId);
    if (projectCard) {
      // This relies on the child component handling the rotation logic
    }
  }, 7000);
};

onMounted(() => {
  projects.value.forEach((project) => {
    rotateProfile(project.id);
  });
});

onUnmounted(() => {
  Object.values(intervals.value).forEach((interval) => {
    clearInterval(interval);
  });
});
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
</style>