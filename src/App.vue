<script setup>
import Navbar from './components/Navbar.vue';
import Tasks from './components/Tasks.vue';
</script>

<template>
  <Navbar />
  <section class="section">
    <div class="container is-medium" style="max-width: 600px;">
      <Tasks />
    </div>
  </section>
</template>

<style scoped>
@import "https://cdn.jsdelivr.net/npm/bulma@0.9.4/css/bulma.min.css";
</style>
