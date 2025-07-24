<template>
  <div>
    <Navbar style="position: sticky; top: 0; z-index: 1000"></Navbar>
    <Home></Home>
    <About></About>
    <Skills></Skills>
    <Project></Project>
  </div>
</template>

<script setup>
import Navbar from "@/components/Navegation/Navbar.vue";
import Home from "@/view/Home.vue";
import About from "@/view/About.vue";
import Skills from "@/view/Skills.vue";
import Project from "@/view/Project.vue";
</script>
