<template>
    <div class="education">
        <img :src='education.image' alt="Education Image" class="education-image" />
        <h2>{{ education.level }}</h2>
        <h3>{{ education.institution }}</h3>
        <p>{{ education.year }}</p>
        <p>{{ education.description }}</p>
        <p>{{  education.standing }}</p>
    </div>
  </template>
  
  <script setup>
  const props = defineProps({
    education: {
      type: Object,
      required: true
    }
  })
  </script>
  