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
  <div class="compliance-guide">
    <div class="header">
      <h2 class="title">Your Monthly Compliance Guide</h2>
      <p class="description">
        The Finance Magnates Compliance Industry Report provides an overview of
        key regulatory changes to help businesses navigate compliance challenges
      </p>
    </div>
    <div class="items-grid">
      <div v-for="item in MOCK_DATA" :key="item.title" class="item">
        <h4 class="item-title">{{ item.title }}</h4>
        <p class="item-text">{{ item.text }}</p>
      </div>
    </div>
    <div class="action">
      <button class="report-button">Get Free Report</button>
    </div>
  </div>
</template>

<style scoped>
.compliance-guide {
  width: 100%;
  background-color: var(--color-background-soft);
  color: var(--color-white);
  padding: 40px 20px;
}

.header {
  margin: 0 auto;
  max-width: 1200px;
}

.title {
  font-size: 36px;
  font-weight: 600;
  margin-bottom: 15px;
  color: var(--color-white);
}

.description {
  font-size: 20px;
  line-height: 1.5;
  color: var(--color-gray);
  margin-bottom: 30px;
}

.items-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 30px;
  max-width: 1200px;
  margin: 0 auto;
}

.item {
  margin-bottom: 20px;
  max-width: 350px;
}

.item-title {
  font-size: 20px;
  font-weight: 600;
  margin-bottom: 10px;
  color: #fff;
  max-width: 350px;
}

.item-text {
  font-size: 16px;
  line-height: 1.4;
  color: #aaa;
  max-width: 350px;
}

.action {
  margin-top: 30px;
  text-align: center;
}

.report-button {
  background-color: var(--color-primary);
  color: white;
  border: none;
  border-radius: 5px;
  padding: 12px 25px;
  font-size: 16px;
  cursor: pointer;
  width: 100%;
  max-width: 1200px;
  &:hover {
    background-color: var(--color-primary-hover);
  }
}

@media (max-width: 768px) {
  .items-grid {
    grid-template-columns: 1fr;
  }
}

@media (min-width: 769px) and (max-width: 1024px) {
  .items-grid {
    grid-template-columns: repeat(2, 1fr);
  }
}
</style>
