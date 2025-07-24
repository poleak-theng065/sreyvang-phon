<template>
  <div
    class="bg-gradient-to-br from-gray-900 to-black text-white p-2 flex flex-col items-center justify-center min-h-screen py-12"
    id="skills"
  >
    <SkillsHeader />
    <SkillsMainContent />
  </div>
</template>

<script setup>
import SkillsHeader from '@/components/Skills/SkillsHeader.vue';
import SkillsMainContent from '@/components/Skills/SkillsMainContent.vue';
</script>