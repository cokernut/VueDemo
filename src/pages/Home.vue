<template>
    <div class="p-4">
      <h1 class="text-2xl font-bold mb-4">Home Page</h1>
      <p class="text-lg mb-4">Received response: {{ response }}</p>
      <NavigationButton @click="navigateToAbout" text="Go to About" />
    </div>
  </template>
  
  <script setup lang="ts">
  import { useRouter, useRoute } from 'vue-router';
  import NavigationButton from '../components/NavigationButton.vue';
  
  const router = useRouter();
  const route = useRoute();
  const response = route.query.response || 'No response received';
  
  function navigateToAbout() {
    router.push({ name: 'About', query: { message: 'Hello from Home!' } });
  }
  </script>
  