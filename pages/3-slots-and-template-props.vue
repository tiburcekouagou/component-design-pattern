<script setup lang="ts">
const loading = ref(false)

watch(loading, async () => {
  if (loading.value) {
    await sleep(2000)
    loading.value = false
  }
})
</script>

<template>
  <div>
    <PageHeading :number="3">Slots and Template Props Pattern</PageHeading>
    <div class="flex gap-3">
      <AppButton :outline="true" :loading="loading" @click="loading = true" >
        <strong>Click Me</strong>
      </AppButton>
    </div>
  </div>
</template>

<style scoped></style>
