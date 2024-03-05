<script setup lang="ts">
const route = useRoute()
</script>

<template>
  <div class="container">
    <div class="flex items-center justify-center">Leaderboard {{ route.params.id }}</div>
  </div>
</template>