<script setup lang="ts">
import facebookIcon from "@/assets/icons/facebook.svg";
import telegramIcon from "@/assets/icons/telegram.svg";
import youtubeIcon from "@/assets/icons/youtube.svg";
import xIcon from "@/assets/icons/x.svg"; // Twitter is now X
import linkedinIcon from "@/assets/icons/linkedin.svg";
import rssIcon from "@/assets/icons/rss.svg";
import footerLogo from "@/assets/footerLogo.png";

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

</script>

<template>
  <footer>
    <div class="footer-branding">
      <img alt="company logo" :src="footerLogo" class="logo" />
    </div>
    <div class="footer-disclaimer">
      <p>
        Finance Magnates Intelligence, part of Finance Magnates, delivers
        specialized research and insights on the financial markets. Offering
        Quarterly, Annual, and custom reports tailored to specific business
        needs, it covers key aspects such as trading volumes, market trends,
        regulations, and more
      </p>
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
    <div class="nav-links">
      <ul>
        <li v-for="link in navLinks" :key="link.text">
          <a :href="link.url">{{ link.text }}</a>
        </li>
      </ul>
    </div>
  </footer>
</template>

<style scoped>
footer {
  display: flex;
  flex-direction: row;
  align-items: flex-start;
  width: 100%;
  padding: 20px;
  box-sizing: border-box;
  color: var(--color-gray);
}

.logo {
  height: 195px;
}

.footer-branding {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  width: 100%;
  max-width: 1400px;
  padding: 0 20px;
  box-sizing: border-box;
}

.footer-disclaimer {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: flex-start;
  width: 100%;
  max-width: 1400px;
  padding: 0 20px;
  box-sizing: border-box;
}

.nav-links {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  width: 100%;
  max-width: 1400px;
  padding: 0 20px;
  box-sizing: border-box;
}

.nav-links ul {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  width: 100%;
  box-sizing: border-box;
}

.nav-links ul li {
  display: flex;
  flex-direction: row;
  justify-content: flex-start;
  align-items: center;
  width: 100%;
  box-sizing: border-box;
}

.nav-links ul li a {
  text-decoration: none;
  color: var(--color-text);
}
</style>
