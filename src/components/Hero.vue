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
}

.hero-content {
  max-width: 636px;
  padding: 40px 20px;
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

</style>
