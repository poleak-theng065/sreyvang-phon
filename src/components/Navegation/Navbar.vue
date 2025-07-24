<template>
  <div>
    <nav
      class="flex flex-wrap items-center justify-between gap-4 py-2 px-4 sm:px-8 md:px-12 lg:px-16 bg-black"
    >
      <!-- Logo Section -->
      <div id="logo" class="flex items-center gap-2 m-2 sm:m-4 order-1">
        <img
          src="@/assets/img/icon/cancer.svg"
          alt="Logo"
          class="h-16 w-16 sm:h-14 sm:w-14 md:h-16 md:w-16 filter-red"
        />
      </div>

      <!-- Mobile Menu Button -->
      <button
        @click="toggleMenu"
        class="md:hidden order-2 p-2 text-lime-500 focus:outline-none"
        aria-label="Toggle menu"
      >
        <span
          class="material-symbols-outlined text-base sm:text-lg md:text-2xl"
        >
          {{ isMenuOpen ? "dehaze" : "dehaze" }}
        </span>
      </button>

      <!-- Navigation Items - Hidden on mobile when menu is closed -->
      <div
        class="w-full md:w-auto order-4 md:order-3"
        :class="{ 'hidden md:flex': !isMenuOpen, flex: isMenuOpen }"
      >
        <ul
          class="flex flex-col md:flex-row items-center gap-2 sm:gap-4 w-full md:w-auto"
        >
          <NavItem
            v-for="item in items"
            :key="item.path"
            :item="item"
          ></NavItem>
        </ul>
      </div>

      <!-- Buttons - Hidden on mobile when menu is closed -->
      <div
        id="button-active"
        class="w-full md:w-auto order-3 md:order-4"
        :class="{ 'hidden md:flex': !isMenuOpen, flex: isMenuOpen }"
      >
        <div
          class="flex flex-col sm:flex-row items-center gap-2 sm:gap-4 w-full md:w-auto"
        >
          <Button
            v-for="button in buttons"
            :key="button.name"
            :button="button"
          ></Button>
        </div>
      </div>
    </nav>
  </div>
</template>

<script setup>
import NavItem from "@/components/Navegation/NavItem.vue";
import Button from "@/components/Navegation/Button.vue";
import { ref } from "vue";

const isMenuOpen = ref(false);

const toggleMenu = () => {
  isMenuOpen.value = !isMenuOpen.value;
};

const items = ref([
  { label: "Home", path: "#home", icon: "home" },
  { label: "About Me", path: "#about", icon: "person" },
  { label: "Skill", path: "#skills", icon: "touchpad_mouse" },
  { label: "Project", path: "#project", icon: "lightbulb" },
  { label: "Contact", path: "#contact", icon: "contacts" },
]);

const buttons = ref([
  {
    name: "Call Me",
    icon: "call",
    class:
      "flex items-center justify-center gap-1 px-3 py-1 sm:px-4 sm:py-2 rounded font-semibold shadow text-lime-500 bg-black border border-lime-500 transition-all duration-200 hover:-translate-y-1 hover:text-black hover:bg-lime-500 focus:outline-none focus:ring-2 focus:ring-lime-500 text-sm sm:text-base w-full sm:w-auto",
  },
  {
    name: "Download CV",
    icon: "download",
    class:
      "flex items-center justify-center gap-1 px-3 py-1 sm:px-4 sm:py-2 rounded font-semibold shadow text-black bg-lime-500 border border-lime-500 transition-all duration-200 hover:-translate-y-1 hover:text-lime-500 hover:bg-black focus:outline-none focus:ring-2 focus:ring-lime-500 text-sm sm:text-base w-full sm:w-auto",
  },
]);
</script>

<style scoped>
@import url("https://fonts.googleapis.com/css2?family=Orbitron:wght@400;500;600;700&display=swap");

#logo h1 {
  font-family: "Orbitron", sans-serif;
  font-weight: 600;
}

nav {
  position: relative;
  z-index: 50;
}

/* Smooth transition for mobile menu */
div[class*="order-"] {
  transition: all 0.3s ease;
}

.filter-red {
  filter: invert(66%) sepia(86%) saturate(787%) hue-rotate(32deg)
    brightness(94%) contrast(101%);
}
</style>
