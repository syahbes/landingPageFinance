<script setup lang="ts">
import { ref } from "vue";
import team1 from "@/assets/images/team1.png";
import team2 from "@/assets/images/team2.png";
import team3 from "@/assets/images/team3.png";
// Define team members data
const teamMembers = [
  {
    id: 1,
    name: "Sylwester Majewski",
    photo: team1, // Replace with actual path
    bio: "A graduate of the Warsaw School of Economics, Sylwester received an MA specializing in finance and banking. As Finance Magnates' research associate and STA certified analyst, he leaves no stone unturned. Sylwester is the previous minority partner of an NFA registered US forex broker, and since 2009, has participated in many forex projects.",
  },
  {
    id: 2,
    name: "Ramzi Ahmad",
    photo: team2, // Replace with actual path
    bio: "With over 16 years of experience in data-driven marketing within the financial industry, Ramzi Ahmad has developed expertise across Fintech, Crypto Payments, and Online Trading markets. He has led teams to improve efficiency and drive growth for dozens of financial brands through actionable data insights. Ramzi continues to advance his skills through courses at institutions like Harvard and Cambridge, ensuring the highest standards of data accuracy.",
  },
  {
    id: 3,
    name: "Damian Chmiel",
    photo: team3,
    bio: "Damian's adventure with the financial markets began at the Cracow University of Economics, where obtained his MA in finance and accounting. Starting from the retail trader perspective, he collaborated with brokerage houses and financial portals in Poland as an independent editor and content manager. His adventure in Finance Magnates began in 2016 where he develops as a business intelligence analyst.",
  },
];

// Current slide index for pagination
const currentSlide = ref(0);

// Function to change slide
const setSlide = (index: number) => {
  currentSlide.value = index;

  // Update to scroll to the selected card in mobile view
  const container = document.querySelector(".team-members-grid");
  const cards = document.querySelectorAll(".team-member-card");

  if (container && cards && cards[index]) {
    // Get the card element and cast to HTMLElement to access offsetLeft
    const card = cards[index] as HTMLElement;
    const containerElement = container as HTMLElement;

    // Scroll to the card with smooth behavior
    container.scrollTo({
      left:
        card.offsetLeft -
        containerElement.offsetWidth / 2 +
        card.offsetWidth / 2,
      behavior: "smooth",
    });
  }
};

// New functions for scrolling on mobile
const scrollLeft = () => {
  const container = document.querySelector(".team-members-grid");
  if (container) {
    container.scrollBy({ left: -350, behavior: "smooth" });
  }
};

const scrollRight = () => {
  const container = document.querySelector(".team-members-grid");
  if (container) {
    container.scrollBy({ left: 350, behavior: "smooth" });
  }
};
</script>

<template>
  <div class="team-wrapper">
    <div class="team-container">
      <div class="team-header">
        <h2>Prepared by industry experts</h2>
        <p>Meet our Team behind our intelligence insights.</p>
      </div>

      <div class="scroll-container">
        <!-- Add scroll buttons for mobile -->
        <button class="scroll-btn prev-btn" @click="scrollLeft">←</button>

        <div class="team-members-grid">
          <div
            v-for="(member, index) in teamMembers"
            :key="member.id"
            class="team-member-card"
            :class="{ active: index === currentSlide }"
            @click="setSlide(index)"
          >
            <div class="member-photo">
              <img :src="member.photo" :alt="member.name" />
            </div>
            <h3 class="member-name">{{ member.name }}</h3>
            <p class="member-bio">{{ member.bio }}</p>
          </div>
        </div>

        <!-- Add scroll buttons for mobile -->
        <button class="scroll-btn next-btn" @click="scrollRight">→</button>
      </div>

      <div class="pagination">
        <span
          v-for="(_, index) in teamMembers"
          :key="index"
          class="dot"
          :class="{ active: index === currentSlide }"
          @click="setSlide(index)"
        ></span>
      </div>
    </div>
  </div>
</template>

// The main change is removing the fixed height and overflow-y for the bio
element // and adjusting the card height on small devices

<style scoped>
.team-wrapper {
  width: 100vw;
  margin-left: calc(-50vw + 50%);
  background-color: var(--color-background-soft);
  padding: 80px 0;
  display: flex;
  justify-content: center;
}

.team-container {
  width: 100%;
  max-width: 1200px;
  padding: 0 20px;
  box-sizing: border-box;
}

.team-header {
  text-align: left;
  margin-bottom: 50px;
}

.team-header h2 {
  font-size: 36px;
  font-weight: 600;
  color: var(--color-white);
  margin: 0 0 10px 0;
}

.team-header p {
  font-size: 18px;
  color: var(--color-gray);
  margin: 0;
}

.scroll-container {
  position: relative;
  width: 100%;
  display: flex;
  align-items: center;
}

.scroll-btn {
  display: none; /* Hidden on desktop */
  background-color: rgba(0, 0, 0, 0.5);
  color: white;
  border: none;
  border-radius: 50%;
  width: 40px;
  height: 40px;
  font-size: 20px;
  cursor: pointer;
  z-index: 10;
  position: absolute;
}

.prev-btn {
  left: 0;
}

.next-btn {
  right: 0;
}

.team-members-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 30px;
}

.team-member-card {
  border-radius: 10px;
  overflow: hidden;
  padding-bottom: 20px;
  width: 378px;
  box-sizing: border-box;
  border: 1px solid transparent;
  background-clip: padding-box, border-box;
  background-origin: border-box;
  background-image: linear-gradient(
      var(--color-background),
      var(--color-background)
    ),
    linear-gradient(180deg, #535455, var(--color-background));
}

.member-photo {
  width: 100%;
  /* height: 260px; */
  width: 314px;
  overflow: hidden;
  border-radius: 8px;
  margin: 30px auto;
}

.member-photo img {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

.member-name {
  font-size: 20px;
  font-weight: 600;
  color: var(--color-white);
  margin: 15px 15px 10px;
}

.member-bio {
  font-size: 14px;
  line-height: 1.5;
  color: var(--color-gray);
  margin: 0 15px;
  /* Removed fixed height and overflow-y to prevent scrolling */
}

.pagination {
  display: flex;
  justify-content: center;
  gap: 10px;
  margin-top: 30px;
}

.dot {
  width: 10px;
  height: 10px;
  border-radius: 50%;
  background-color: #333;
  cursor: pointer;
  transition: background-color 0.3s;
}

.dot.active {
  background-color: var(--color-white);
}

/* Media queries for responsiveness */
@media (max-width: 992px) {
  .team-members-grid {
    display: flex;
    overflow-x: auto;
    scroll-snap-type: x mandatory;
    padding: 10px 5px;
    gap: 20px;
    scrollbar-width: none; /* Hide scrollbar for Firefox */
    -ms-overflow-style: none; /* Hide scrollbar for IE and Edge */
  }

  .team-members-grid::-webkit-scrollbar {
    display: none; /* Hide scrollbar for Chrome, Safari and Opera */
  }

  .team-member-card {
    flex: 0 0 auto;
    width: 80%;
    max-width: 350px;
    scroll-snap-align: center;
    cursor: pointer;
    transition: transform 0.3s ease;
  }

  .team-member-card.active {
    transform: translateY(-5px);
    box-shadow: 0 5px 15px rgba(0, 0, 0, 0.3);
  }

  .scroll-btn {
    display: block;
  }
}

@media (max-width: 576px) {
  .team-members-grid {
    padding: 10px 0;
  }

  .team-member-card {
    width: 90%;
    max-width: 300px;
    /* Auto height to fit content without scrolling */
    height: auto;
  }

  .team-header h2 {
    font-size: 28px;
  }

  .team-header p {
    font-size: 16px;
  }

  .member-photo {
    width: 90%;
    max-width: 280px;
  }

  .member-photo img {
    width: 100%;
    height: auto;
  }

  .member-bio {
    /* Removed fixed height and max-height to allow full content display */
    height: auto;
  }
}
</style>
