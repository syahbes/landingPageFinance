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
  padding: 0 20px;
  box-sizing: border-box;
}

.hero-content {
  max-width: 636px;
  padding: 40px 0;
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
}

/* Media queries for responsiveness */
@media (max-width: 1200px) {
  h1 {
    font-size: 48px;
    line-height: 58px;
  }

  h3 {
    font-size: 18px;
    line-height: 28px;
  }
}

@media (max-width: 992px) {
  .hero-container {
    flex-direction: column;
    gap: 30px;
  }

  .hero-content {
    max-width: 100%;
    padding: 30px 0 0 0;
    text-align: center;
  }
}

@media (max-width: 576px) {
  h1 {
    font-size: 36px;
    line-height: 44px;
  }

  h3 {
    font-size: 16px;
    line-height: 24px;
  }
}
</style>
