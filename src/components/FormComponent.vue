<script setup lang="ts">
import { ref } from "vue";

// Define the form data type with an index signature
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

  // Reset form
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
    <form @submit.prevent="handleSubmit">
      <h3>Get your free compliance guide</h3>
      <div v-for="field in fields" :key="field.name">
        <label :for="field.name">{{ field.label }}</label>
        <input
          :id="field.name"
          :type="field.type"
          :placeholder="field.placeholder"
          v-model="formData[field.name]"
        />
      </div>
      <button type="submit">Submit</button>
    </form>
  </div>
</template>

<style scoped>
.form-container {
  border: 1px solid #e5e7eb;
  width: 576px;
}
</style>
