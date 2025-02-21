<script setup lang="ts">
import type { UserData } from '~/types';

const props = defineProps<{
  username: string,
}>()

const loading = ref(true)
const userData = ref<UserData | null>(null)

fetch(`https://api.github.com/users/${props.username}`)
  .then(async (response) => {
    await sleep(2000)
    userData.value = await response.json()
  })
  .catch((error) => {
    console.error('Error fetching Github data:', error);

  })
  .finally(() => {
    loading.value = false
  })
</script>

<template>
  <div class="card bg-base-100 shadow-xl max-w-sm w-[350px]">
    <!-- Loading State -->
    <GithubCardSkeleton v-if="loading || !userData" />

    <!-- Loaded State -->
    <GithubCardContent v-else :user-data="userData" />
  </div>
</template>

<style scoped></style>
