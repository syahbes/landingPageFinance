<script setup lang="ts"></script>

<template>
  <div class="form-wrapper">
    <div class="blue-blob"></div>
    <div class="form-container">
      <form action="">
        <h2>Get your free compliance guide</h2>

        <div class="form-group">
          <label for="firstName">First name</label>
          <input type="text" id="firstName" placeholder="John" />
        </div>

        <div class="form-group">
          <label for="lastName">Last name</label>
          <input type="text" id="lastName" placeholder="Doe" />
        </div>

        <div class="form-group">
          <label for="email">Email Address</label>
          <input type="email" id="email" placeholder="you@company.com" />
        </div>

        <div class="form-group">
          <label for="company">Company</label>
          <input type="text" id="company" placeholder="Enter company name" />
        </div>

        <button type="submit">Get Free Report</button>

        <div class="privacy-notice">
          <p>
            By submitting this form, you agree to our
            <a href="#">Privacy Policy</a>.
          </p>
          <p>
            This site is protected by reCAPTCHA and the Google
            <a href="#">Privacy Policy</a> and
            <a href="#">Terms of Service</a> apply.
          </p>
        </div>
      </form>
    </div>
  </div>
</template>

<style scoped>
.form-wrapper {
  position: relative;
  width: 460px;
}

.blue-blob {
  position: absolute;
  width: 700px;
  height: 900px;
  background: radial-gradient(
    circle at center,
    #1543bf 0%,
    rgba(21, 67, 191, 0.2) 40%,
    rgba(21, 67, 191, 0) 70%
  );
  filter: blur(60px);
  z-index: 0;
  top: 25%;
  left: 20%;
  transform: translate(-50%, -50%);
  pointer-events: none;
}

.form-container {
  position: relative;
  z-index: 1;
  background-color: var(--color-background-soft);
  /* backdrop-filter: blur(10px); */
  border-radius: 12px;
  padding: 32px;
  width: 100%;
}

/* Create gradient background with pseudo-element */
.form-container::before {
  content: "";
  position: absolute;
  top: -1px;
  left: -1px;
  right: -1px;
  bottom: -1px;
  background: linear-gradient(to right, #acaeb7, #4c4d51);
  border-radius: 12px; /* Slightly larger than container */
  z-index: -2;
}

/* Create inner "hole" with same background as container */
.form-container::after {
  content: "";
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: var(--color-background-soft);
  border-radius: 12px; /* Slightly smaller than container */
  z-index: -1;
}
form {
  display: flex;
  flex-direction: column;
  gap: 20px;
}

h2 {
  font-size: 24px;
  font-weight: 600;
  margin-bottom: 12px;
}

.form-group {
  display: flex;
  flex-direction: column;
  gap: 8px;
}

label {
  font-size: 14px;
  color: var(--color-white);
}

input {
  padding: 12px 16px;
  background-color: rgba(10, 11, 13, 0.5);
  border: 1px solid rgba(255, 255, 255, 0.1);
  border-radius: 4px;
  color: var(--color-white);
  font-size: 16px;
}

button {
  background-color: #1543bf;
  color: white;
  border: none;
  border-radius: 4px;
  padding: 14px;
  font-size: 16px;
  font-weight: 600;
  cursor: pointer;
  transition: background-color 0.2s;
}

button:hover {
  background-color: #1a50d9;
}

.privacy-notice {
  font-size: 12px;
  color: rgba(255, 255, 255, 0.7);
}

.privacy-notice p {
  margin: 4px 0;
}

.privacy-notice a {
  color: var(--color-white);
  text-decoration: underline;
}
</style>
