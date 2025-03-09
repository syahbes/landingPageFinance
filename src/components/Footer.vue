<script setup lang="ts">
import facebookIcon from "@/assets/icons/facebook.svg";
import telegramIcon from "@/assets/icons/telegram.svg";
import youtubeIcon from "@/assets/icons/youtube.svg";
import xIcon from "@/assets/icons/x.svg"; // Twitter is now X
import linkedinIcon from "@/assets/icons/linkedin.svg";
import rssIcon from "@/assets/icons/rss.svg";

const socialLinks = [
  { icon: xIcon, url: "#", ariaLabel: "X (Twitter)" },
  { icon: telegramIcon, url: "#", ariaLabel: "Telegram" },
  { icon: youtubeIcon, url: "#", ariaLabel: "YouTube" },
  { icon: facebookIcon, url: "#", ariaLabel: "Facebook" },
  { icon: linkedinIcon, url: "#", ariaLabel: "LinkedIn" },
  { icon: rssIcon, url: "#", ariaLabel: "RSS Feed" },
];

const navLinks = [
  { text: "Finance Magnates", url: "#" },
  { text: "Latest News", url: "#" },
  { text: "Directory", url: "#" },
  { text: "Events", url: "#" },
  { text: "Contact Us", url: "#" },
];

const legalLinks = [
  { text: "Cookie Policy", url: "#" },
  { text: "Privacy Policy", url: "#" },
  { text: "Terms and Conditions", url: "#" },
  { text: "Manage Cookies", url: "#" },
];
</script>

<template>
  <footer>
    <div class="footer-top">
      <div class="logos-container">
        <img
          alt="Finance Magnates logo"
          src="@/assets/logo.svg"
          class="logo-primary"
        />
        <img
          alt="Finance Magnates logo"
          src="@/assets/union.png"
          class="logo-secondary"
        />
      </div>
      <div class="footer-info-container">
        <div class="text-and-social">
          <div class="text">
            <p>
              Finance Magnates Intelligence, part of Finance Magnates, delivers
              specialized research and insights on the financial markets.
              Offering Quarterly, Annual, and custom reports tailored to
              specific business needs, it covers key aspects such as trading
              volumes, market trends, regulations, and more
            </p>
          </div>
          <div class="social-links">
            <a
              v-for="(link, index) in socialLinks"
              :key="index"
              :href="link.url"
              :aria-label="link.ariaLabel"
              class="social-link"
            >
              <img :src="link.icon" :alt="link.ariaLabel" class="social-icon" />
            </a>
          </div>
        </div>
        <nav class="footer-nav">
          <ul>
            <li v-for="link in navLinks" :key="link.text">
              <a :href="link.url">{{ link.text }}</a>
            </li>
          </ul>
        </nav>
      </div>
    </div>

    <div>
      <div class="footer-bottom">
        <div class="copyright">
          <p>© 2025 "Finance Magnates CY Ltd." All rights reserved.</p>
        </div>

        <div class="legal-links">
          <ul>
            <li v-for="(link, index) in legalLinks" :key="index">
              <a :href="link.url">{{ link.text }}</a>
              <span
                v-if="index < legalLinks.length - 1"
                class="separator"
              ></span>
            </li>
          </ul>
        </div>
      </div>
    </div>
  </footer>
</template>

<style>
p {
  margin: 0;
  padding: 0;
  color: var(--color-gray);
}
.social-link {
  display: inline-block;
  margin-right: 10px;
  transition: all 0.3s ease;
  &:hover {
    opacity: 0.8;
    scale: 1.1;
  }
}
.footer-nav ul,
.legal-links ul {
  list-style: none;
  padding: 0;
  margin: 0;
}

.footer-nav li {
  margin-bottom: 5px;
  width: 200px;
}

.footer-nav a,
.legal-links a {
  color: var(--color-gray);
  text-decoration: none;
  /* hover */
  &:hover {
    color: aliceblue;
  }
}

.footer-top {
  max-width: 1440px;
  width: 100%;
  margin: auto;
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: start;
  gap: 50px;
  padding: 20px 10px;
}

.logos-container {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  align-items: center;
  gap: 20px;
}
.footer-info-container {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: flex-start;
  gap: 20px;
}
.text-and-social {
  display: flex;
  flex-direction: column;
  gap: 40px;
}
.footer-bottom {
  max-width: 1440px;
  width: 100%;
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  padding: 30px 0;
}

.legal-links ul {
  display: flex;
  flex-direction: row;
  gap: 10px;
}

/* @media (max-width: 922px) {
  .logos-container {
    max-width: 640px;
    width: 100%;
    margin: auto;
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    align-items: center;
  }
  .logo-primary {
    width: 195px;
  }
  .logo-secondary {
    width: 172px;
  }
  .footer-info-container {
    max-width: 640px;
    width: 100%;
    margin: auto;
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    align-items: center;
  }
} */
</style>
