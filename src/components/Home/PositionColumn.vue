<template>
  <div
    class="flex flex-col gap-4 space-y-6 lg:space-y-8 items-center lg:items-start"
  >
    <h2
      class="text-2xl md:text-3xl lg:text-4xl font-medium tracking-wide text-gray-300 animate-fade-in-down"
    >
      Interest on
    </h2>
    <h2
      class="text-2xl sm:text-3xl md:text-4xl lg:text-5xl font-extrabold text-center lg:text-left bg-gradient-to-r from-lime-400 via-blue-400 to-green-400 text-transparent bg-clip-text animate-typewriter border-r-2 border-lime-400 whitespace-nowrap overflow-hidden w-full sm:w-fit"
    >
      Front-End Developer
    </h2>
    <p
      class="text-lg md:text-xl text-gray-300 text-center lg:text-left max-w-md leading-relaxed animate-fade-in-up delay-100"
    >
      Crafting modern, responsive, and user-friendly web experiences.
    </p>
    <div class="flex space-x-6 md:space-x-8 gap-6">
      <a
        aria-label="LinkedIn"
        class="w-14 h-14 md:w-16 md:h-16 bg-gradient-to-br from-gray-900 to-gray-800 flex items-center justify-center rounded-xl border border-lime-400/30 shadow-lg hover:scale-110 transition-transform duration-300 text-lime-400"
        href="https://www.linkedin.com/in/sreyvangphon"
        rel="noopener noreferrer"
        target="_blank"
      >
        <i class="fab fa-linkedin-in text-2xl md:text-3xl"> </i>
      </a>
      <a
        aria-label="GitHub"
        class="w-14 h-14 md:w-16 md:h-16 bg-gradient-to-br from-gray-900 to-gray-800 flex items-center justify-center rounded-xl border border-lime-400/30 shadow-lg hover:scale-110 transition-transform duration-300 text-lime-400"
        href="https://github.com/sreyvangphon"
        rel="noopener noreferrer"
        target="_blank"
      >
        <i class="fab fa-github text-2xl md:text-3xl"> </i>
      </a>
      <a
        aria-label="Telegram"
        class="w-14 h-14 md:w-16 md:h-16 bg-gradient-to-br from-gray-900 to-gray-800 flex items-center justify-center rounded-xl border border-lime-400/30 shadow-lg hover:scale-110 transition-transform duration-300 text-lime-400"
        href="https://t.me/sreyvangphon"
        rel="noopener noreferrer"
        target="_blank"
      >
        <i class="fab fa-telegram-plane text-2xl md:text-3xl"> </i>
      </a>
      <a
        aria-label="Email"
        class="w-14 h-14 md:w-16 md:h-16 bg-gradient-to-br from-gray-900 to-gray-800 flex items-center justify-center rounded-xl border border-lime-400/30 shadow-lg hover:scale-110 transition-transform duration-300 text-lime-400"
        href="mailto:sreyvang.phon@example.com"
      >
        <i class="fas fa-envelope text-2xl md:text-3xl"> </i>
      </a>
    </div>
    <a
      class="flex items-center justify-center gap-2 mt-3 bg-gradient-to-r from-lime-400 via-lime-500 to-green-400 hover:from-lime-500 hover:to-green-500 text-black font-extrabold py-3 px-6 rounded-xl text-base md:text-lg transition-all duration-300 w-full text-center shadow-lg ring-2 ring-lime-400/30 animate-fade-in-up delay-200"
      href="#"
    >
      <span class="material-symbols-outlined"> download </span>
      Download CV
    </a>
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
@keyframes fade-in-up {
  0% {
    opacity: 0;
    transform: translateY(30px);
  }
  100% {
    opacity: 1;
    transform: translateY(0);
  }
}
@keyframes typewriter {
  0% {
    width: 0;
  }
  40% {
    width: 17ch;
  }
  50% {
    width: 17ch; /* Pause fully typed */
  }
  90% {
    width: 0; /* Erase back */
  }
  100% {
    width: 0;
  }
}

.animate-typewriter {
  animation: typewriter 6s steps(24) infinite;
  white-space: nowrap;
  overflow: hidden;
  border-right: 2px solid #a3e635; /* lime-400 */
}
</style>