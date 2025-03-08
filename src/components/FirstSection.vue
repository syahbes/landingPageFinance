<script setup lang="ts">
const MOCK_DATA = [
  {
    title: "Regulatory Updates",
    text: "Explore the latest changes from major regulators so you can adjust your operations confidently.",
  },
  {
    title: "Key Announcements",
    text: "Keep up with important notices and advisories that may impact your business.",
  },
  {
    title: "Fines, Penalties & Seizures",
    text: "Explore enforcement actions, including fines, to understand risks and stay ahead of compliance challenges",
  },
  {
    title: "Scam Alerts",
    text: "Protect your company by staying aware of frauds and scams making waves in the industry.",
  },
  {
    title: "Compliance Experts Insights",
    text: "Gain valuable perspectives from industry compliance experts from leading firms",
  },
  {
    title: "Domestic Insurance News",
    text: "Track shifts in domestic insurance regulations to keep your business compliant",
  },
];
</script>

<template>
  <div class="first-section">
    <div>
      <h3>Your Monthly Compliance Guide</h3>
      <p>
        The Finance Magnates Compliance Industry Report provides an overview of
        key regulatory changes to help businesses navigate compliance challenges
      </p>
    </div>
    <div>
      <div v-for="item in MOCK_DATA" :key="item.title">
        <h4>{{ item.title }}</h4>
        <p>{{ item.text }}</p>
      </div>
    </div>
  </div>
</template>

<style scoped>
.first-section {
  width: 100%;
  background-color: var(--color-background-soft);
  padding: 40px 20px;
}
</style>
