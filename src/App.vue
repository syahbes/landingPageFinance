<script setup lang="ts">
import Hero from "./components/Hero.vue";
import ComplianceGuide from "./components/ComplianceGuide.vue";
import FAQ from "./components/FAQ.vue";
import Team from "./components/Team.vue";
</script>

<template>
  <header>
    <img alt="company logo" src="./assets/logo.svg" class="logo" />
  </header>

  <main>
    <Hero />
    <ComplianceGuide />
    <FAQ />
    <Team />
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
  overflow-x: hidden;
  gap: 40px;
}

@media (max-width: 576px) {
  .logo {
    width: 150px;
    height: auto;
  }
}
</style>
