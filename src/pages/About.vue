<template>
    <div>
      <h1>About Page</h1>
      <p>Received message: {{ message }}</p>
      <NavigationButton @click="goBack" text="Go Back to Home" />
    </div>
  </template>
  
  <script setup lang="ts">
  import { useRouter, useRoute } from 'vue-router';
  import NavigationButton from '../components/NavigationButton.vue';
  
  const route = useRoute();
  const router = useRouter();
  const message = route.query.message || 'No message received';
  
  function goBack() {
    router.push({ name: 'Home', query: { response: 'Hello from About!' } });
  }
  </script>
  