<template>
    <button @click="handleClick">{{ text }}</button>
  </template>
  
  <script setup lang="ts">
  import { defineProps, defineEmits } from 'vue';
  
  const props = defineProps<{ text: string }>();
  const emit = defineEmits<{
    (e: 'click'): void;
  }>();
  
  function handleClick() {
    emit('click');
  }
  </script>
  