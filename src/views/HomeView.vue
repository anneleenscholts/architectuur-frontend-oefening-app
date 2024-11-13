<script setup lang="ts">
import { useRouter } from 'vue-router'
const router = useRouter();
</script>

<template>
  <div class="home">
    <nav>
      <button class="btn" @click="router.push({ 'name': 'home' })">Home</button>
      <button class="btn" @click="router.push({ 'name': 'about' })">About</button>
    </nav>
    <h1>This is a home page</h1>
  </div>
</template>

<style scoped>
@media (min-width: 1024px) {
  .home {
    min-height: 100vh;
    display: flex;
    align-items: center;
  }
}

.btn {
  margin: 0.3rem;
}
</style>
