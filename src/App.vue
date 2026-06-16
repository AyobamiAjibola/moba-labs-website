<script setup lang="ts">
import Navbar from '@/components/shared/Navbar.vue';
</script>

<template>
  <Navbar />
  <main class="flex-1">
    <RouterView />
  </main>
</template>
