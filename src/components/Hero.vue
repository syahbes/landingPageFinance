<script setup lang="ts">
import FormComponent from "./FormComponent.vue";
</script>

<template>
  <div class="hero-container">
    <div class="hero-content">
      <h1>Stay Informed.<br />Stay Compliant.</h1>
      <h3>
        Sign up to access the latest Insights on Regulatory Highlights, Recent
        Developments, and Future Outlook—all in one monthly report.
      </h3>
    </div>
    <FormComponent />
  </div>
</template>

<style scoped>
.hero-container {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: center;
  width: 100%;
  padding: 40px 0;
  gap: 40px;
}

.hero-content {
  max-width: 600px;
}

h1 {
  font-weight: 700;
  font-size: 60px;
  line-height: 72px;
  margin-bottom: 24px;
}

h3 {
  font-weight: 400;
  font-size: 20px;
  line-height: 30px;
  max-width: 540px;
}

/* @media (max-width: 1200px) {
  .hero-container {
    flex-direction: column;
    align-items: flex-start;
  }

  h1 {
    font-size: 48px;
    line-height: 60px;
  }
} */
</style>
