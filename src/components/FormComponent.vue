<script setup lang="ts">
import { ref } from "vue";

type FormData = {
  [key: string]: string;
};

const formData = ref<FormData>({
  firstName: "",
  lastName: "",
  email: "",
  company: "",
});

const handleSubmit = () => {
  console.log("Form submitted", { ...formData.value });

  Object.keys(formData.value).forEach((key) => {
    formData.value[key] = "";
  });
};

const fields = [
  { name: "firstName", label: "First Name", type: "text", placeholder: "John" },
  { name: "lastName", label: "Last Name", type: "text", placeholder: "Doe" },
  {
    name: "email",
    label: "Email",
    type: "email",
    placeholder: "you@company.com",
  },
  {
    name: "company",
    label: "Company",
    type: "text",
    placeholder: "Enter Company name",
  },
];
</script>

<template>
  <div class="form-container">
    <div class="blob topBlob"></div>
    <div class="blob midBlob"></div>
    <div class="blob bottomBlob"></div>
    <!-- Add this line for the blob effect -->
    <form @submit.prevent="handleSubmit">
      <div class="form-header">
        <h3>Get your free compliance guide</h3>
      </div>
      <div v-for="field in fields" :key="field.name">
        <label :for="field.name">{{ field.label }}</label>
        <input
          :id="field.name"
          :type="field.type"
          :placeholder="field.placeholder"
          v-model="formData[field.name]"
        />
      </div>
      <button type="submit">Get Free Report</button>
      <div class="privacy-text">
        <span
          >By submitting this form, you agree to our
          <a href="#">Privacy Policy</a>.</span
        >
      </div>
      <div class="recaptcha-text">
        <span
          >This site is protected by reCAPTCHA and the Google Privacy Policy and
          <a href="#">Terms of Service</a> apply.</span
        >
      </div>
    </form>
  </div>
</template>

<style scoped>
.form-container {
  position: relative; /* Add this to position the blob relative to the form */
  width: 100%;
  max-width: 576px;
  margin: 0 auto;
  padding: 40px 20px;
  border-radius: 16px;
  background-color: var(--color-background-soft);
  color: var(--color-gray);
  box-sizing: border-box;
  border: 1px solid transparent;
  background-clip: padding-box, border-box;
  background-origin: border-box;
  background-image: linear-gradient(
      var(--color-background-soft),
      var(--color-background-soft)
    ),
    linear-gradient(45deg, #acaeb7, #4c4d51);
}

/* Alternative without composes - for regular CSS */
.blob {
  position: absolute;
  background: linear-gradient(45deg, #1335f5, #6cace4);
  border-radius: 50%;
  filter: blur(80px);
  z-index: -1;
}

.topBlob {
  top: -205px;
  left: -140px;
  width: 450px;
  height: 600px;
}

.midBlob {
  top: -105px;
  left: 120px;
  width: 250px;
  height: 400px;
}

.bottomBlob {
  bottom: -200px;
  right: -80px;
  width: 300px;
  height: 600px;
}

form {
  display: flex;
  flex-direction: column;
  gap: 20px;
  width: 100%;
  max-width: 480px;
  margin: 0 auto;
}

.form-header {
  display: flex;
  flex-direction: row;
  justify-content: flex-start;
  align-items: center;
  width: 100%;
}
h3 {
  font-size: 24px;
  font-weight: 600;
  margin: 0;
  line-height: 32px;
  text-align: center;
  color: var(--color-white);
}

label {
  display: block;
  font-size: 16px;
  margin-bottom: 8px;
  font-weight: 500;
}

input {
  width: 100%;
  padding: 12px 16px;
  font-size: 16px;
  border: 1px solid #5e5e62;
  border-radius: 4px;
  background-color: var(--color-background-soft);
  color: white;
  box-sizing: border-box;
}

input::placeholder {
  color: #71717a;
}

button {
  margin-top: 10px;
  padding: 14px;
  border: none;
  border-radius: 4px;
  background-color: var(--color-primary);
  color: var(--color-white);
  font-size: 16px;
  font-weight: 600;
  cursor: pointer;
}

button:hover {
  background-color: var(--color-primary-hover);
}

.privacy-text {
  font-size: 14px;
}

.privacy-text a {
  color: var(--color-white);
  text-decoration: underline;
}

.recaptcha-text {
  font-size: 14px;
  color: var(--color-gray);
  word-wrap: break-word;
}

.recaptcha-text a {
  text-decoration: underline;
  color: var(--color-gray);
}

/* Media queries for responsiveness */
@media (max-width: 768px) {
  .form-container {
    padding: 30px 15px;
  }
}

@media (max-width: 576px) {
  h3 {
    font-size: 20px;
  }

  form {
    gap: 15px;
  }
}
</style>
