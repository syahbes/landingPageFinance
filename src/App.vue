<script setup lang="ts">
import FirstSection from "./components/FirstSection.vue";
import Hero from "./components/Hero.vue";
</script>

<template>
  <header>
    <img alt="company logo" src="./assets/logo.svg" class="logo" />
  </header>

  <main>
    <Hero />
    <FirstSection />
    <!-- 3rd section -->
    <!-- 4th section -->
  </main>
  <footer>footer</footer>
</template>

<style scoped>
header {
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: flex-start;
  width: 100%;
  padding: 10px 20px;
  box-sizing: border-box;
}
.logo {
  width: 195px;
  height: 32px;
}
main {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  width: 100%;
  overflow-x: hidden; /* Prevent horizontal scrolling */
  gap: 40px;
}

@media (max-width: 576px) {
  .logo {
    width: 150px;
    height: auto;
  }
}
</style>
