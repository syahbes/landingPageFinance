<script setup lang="ts">
import faq1 from "@/assets/images/faq1.png";
import faq2 from "@/assets/images/faq2.png";
import faq3 from "@/assets/images/faq3.png";

const faqItems = [
  {
    question: "How often is the Compliance Industry Report available?",
    answer:
      "The report is published monthly, providing regular updates to help businesses stay ahead of compliance changes.",
  },
  {
    question: "How can I access the Monthly Compliance Industry Report?",
    answer:
      "Simply fill out the form on this page to get the report delivered straight to your inbox.",
  },
  {
    question: "How is the data in the report gathered?",
    answer:
      "The report uses trusted sources like global regulators, industry news, expert analysis, and input from compliance professionals.",
  },
];

const images = [
  { src: faq1, alt: "Mobile screen showing compliance report" },
  { src: faq2, alt: "Multiple mobile screens showing compliance report" },
  { src: faq3, alt: "Mobile screen showing regulatory intelligence insight" },
];
</script>
<template>
  <div class="faq-wrapper">
    <div class="faq-container">
      <!-- Images Section -->
      <div class="faq-images">
        <img
          v-for="(image, index) in images"
          :key="index"
          :src="image.src"
          :alt="image.alt"
          class="faq-image"
        />
      </div>

      <!-- FAQ Section -->
      <div class="faq-content">
        <h2 class="faq-title">Frequently Asked Questions</h2>
        <div class="faq-items">
          <div v-for="(item, index) in faqItems" :key="index" class="faq-item">
            <h3 class="faq-question">{{ item.question }}</h3>
            <p class="faq-answer">{{ item.answer }}</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.faq-wrapper {
  background-color: #0a0a0a;
  padding: 80px 0;
  display: flex;
  justify-content: center;
  color: white;
}

.faq-container {
  width: 100%;
  max-width: 1200px;
  text-align: center;
}

/* Images Section */
.faq-images {
  display: flex;
  justify-content: center;
  gap: 20px;
  margin-bottom: 50px;
}

.faq-image {
  width: 500px;
  height: 400px;
  border-radius: 10px;
  object-fit: cover;
}

/* FAQ Content */
.faq-title {
  font-size: 36px;
  font-weight: 600;
  margin-bottom: 30px;
  text-align: left;
}

.faq-items {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 30px;
}

.faq-item {
  padding: 20px;
  border-radius: 10px;
  text-align: left;
}

.faq-question {
  font-size: 18px;
  font-weight: 400;
  color: var(--color-white);
  margin-bottom: 5px;
}

.faq-answer {
  font-size: 16px;
  color: var(--color-gray);
  line-height: 1.6;
}

/* Responsive Design */
@media (max-width: 992px) {
  .faq-images {
    flex-direction: column;
    align-items: center;
  }

  .faq-image {
    width: 90%;
    height: auto;
  }
}
</style>
