<script lang="ts" setup>
const route = useRoute()
</script>

<template>
  <NavBar />
  <main class="px-7 py-10">
    <RouterView />
    <Footer :key="route.path" />
  </main>
</template>
