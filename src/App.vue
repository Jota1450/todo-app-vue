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