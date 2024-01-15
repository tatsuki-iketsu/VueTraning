<script setup lang="ts">
import Json from '../components/Json.vue'
</script>

<template>
  <div class="about">
    <h1>Input</h1>
        <Json />
  </div>
</template>

<style>
@media (min-width: 1024px) {
  .about {
    min-height: 100vh;
    display: flex;
    align-items: center;
  }
}
</style>
