<script setup lang="ts">
import Hero from "./components/Hero.vue";
import ComplianceGuide from "./components/ComplianceGuide.vue";
import FAQ from "./components/FAQ.vue";
import Team from "./components/Team.vue";
import Footer from "./components/Footer.vue";
</script>

<template>
  <header>
    <div class="logo-wrapper">
      <img alt="company logo" src="./assets/logo.svg" class="logo" />
    </div>
  </header>

  <main>
    <Hero />
    <ComplianceGuide />
    <FAQ />
    <Team />
  </main>
  <Footer />
</template>

<style scoped>
header {
  padding: 10px;
  position: absolute;
  top: 10px;
  left: 10px;
  background-color: transparent;
  width: 100%;
}
.logo-wrapper {
  max-width: 1400px;
  margin: auto;
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

@media screen and (max-width: 992px) {
  .logo-wrapper {
    padding-left: 25px;
  }
}

@media (max-width: 576px) {
  .logo {
    width: 150px;
    height: auto;
  }
}
</style>
