<script setup lang="ts">
const router = useRouter()

const currentUser = ref<number>(66669420)
const gameStarting = ref<boolean>(false)

const onClickGameStartButton = () => {
  gameStarting.value = true
  setTimeout(() => {
    gameStarting.value = false
    router.push('/game')
  }, 2000)
}

const gameButtonText = computed(() => {
  if (gameStarting.value) return 'Loading...'
  return 'Start match'
})
</script>

<template>
  <nav class="flex justify-between items-center gap-3 px-8 py-4 bg-teal-200 shadow-md">
    <ul class="flex gap-2">
      <li class="hover:text-teal-700 transition-all cursor-pointer"><NuxtLink :to="`/${currentUser}/profile`">Profile</NuxtLink></li>
      <li class="hover:text-teal-700 transition-all cursor-pointer"><NuxtLink :to="`/${currentUser}/achievements`">Achievements</NuxtLink></li>
      <li class="hover:text-teal-700 transition-all cursor-pointer"><NuxtLink :to="`/${currentUser}/leaderboard`">Leaderboard</NuxtLink></li>
    </ul>
    <button class="border border-teal-700 rounded px-2 py-1 shadow hover:shadow-lg transition-all hover:text-teal-900" @click="onClickGameStartButton">
      {{ gameButtonText }}</button>
  </nav>
</template>