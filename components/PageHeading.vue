<script setup lang="ts">
defineProps<{
  number: number
}>()
</script>

<template>
  <div>
    <h1 class="text-3xl mb-10">
      <span class="mb-2 block badge badge-primary badge-outline">Pattern {{ number }}</span>
      <slot></slot>
    </h1>
  </div>
</template>

<style scoped></style>
