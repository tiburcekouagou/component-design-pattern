<script setup lang="ts">
defineProps({
  loading: {type: Boolean, default: false},
  outline: {type: Boolean, default: false}
})
</script>

<template>
  <button class="btn flex items-center" :class="{'btn-outline': outline}">
    <AppSpinner v-if="loading" />
    <slot></slot>
  </button>
</template>

<style scoped></style>
