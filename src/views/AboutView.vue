<script setup lang="ts">
import { useRouter } from 'vue-router'
const router = useRouter();
</script>

<template>
  <div class="about">
    <nav>
      <button class="btn" @click="router.push({ 'name': 'home' })">Home</button>
      <button class="btn" @click="router.push({ 'name': 'about' })">About</button>
    </nav>
    <h1>This is an about page</h1>
  </div>
</template>

<style scoped>
@media (min-width: 1024px) {
  .about {
    min-height: 100vh;
    display: flex;
    align-items: center;
  }
}

.btn {
  margin: 0.3rem;
}
</style>
