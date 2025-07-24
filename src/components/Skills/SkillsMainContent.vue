<template>
  <div class="flex flex-col lg:flex-row gap-8 items-center lg:items-stretch justify-center w-full max-w-9xl px-6">
    <ProfileImage />
    <SkillsSections />
  </div>
</template>

<script setup>
import ProfileImage from './ProfileImage.vue';
import SkillsSections from './SkillsSections.vue';
</script>