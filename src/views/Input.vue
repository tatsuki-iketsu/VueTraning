<script setup lang="ts">
import Json from '../components/Json.vue'
</script>

<template>
  <div class="about">
    <h1>CSS問題</h1>
        <Json />
  </div>
</template>

<style>
@media (min-width: 1024px) {
  .about {
    min-height: 100vh;
    align-items: center;
  }
}
</style>
