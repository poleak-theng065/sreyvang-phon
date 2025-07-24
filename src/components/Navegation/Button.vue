<template>
  <div>
    <button :@click="$emit(button.icon)" :class="button.class">
      <span class="material-symbols-outlined"> {{ button.icon }} </span>
      {{ button.name }}
    </button>
  </div>
</template>

<script setup>
defineProps(["button"]);
</script>

<style lang="scss" scoped></style>
