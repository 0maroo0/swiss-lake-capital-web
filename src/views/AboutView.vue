<template>
  <section id="about" class="section">
    <div class="container">
      <div class="tabs">
        <div
          v-for="(tab, index) in tabs"
          :key="index"
          :class="['tab', { active: activeTab === index }]"
          @click="setActiveTab(index)"
        >
          {{ tab.label }}
        </div>
      </div>

      <div
        v-for="(tab, index) in tabs"
        :key="index"
        v-show="activeTab === index"
        class="tab-content"
      >
        <h2>{{ tab.title }}</h2>
        <p v-if="typeof tab.content === 'string'">{{ tab.content }}</p>
        <div v-else>
          <p>{{ tab.content.main }}</p>
          <p class="highlight-equation">{{ tab.content.equation }}</p>
        </div>
      </div>

      <div class="about-us-section">
        <img
          src="https://greenmarmot.com/images/Logo/LOGO_Green.png"
          alt="About Us"
          class="about-image"
        />
        <div class="about-content">
          <h2>Partner</h2>
          <p>
            Green marmot GmbH is a leading capsule hotel company in Switzerland
            and one of our most promising partners They acquire through short
            period a remarkable footprint in Zurich hotels reviews because of
            their unique central location, high standard hygiene accomodation
            and economic affordable prices
          </p>
        </div>
      </div>
    </div>
  </section>
  <VedioSlider />
  <Reviews />
  <Slider />
</template>

<script>
import VedioSlider from "@/components/vedio_slider.vue";
import Reviews from "@/components/reviews.vue";
import Slider from "@/components/slider.vue";

export default {
  name: "ReputationSection",
  components: {
    VedioSlider,
    Reviews,
    Slider,
  },
  data() {
    return {
      activeTab: 0,
      tabs: [
        {
          label: "Overview",
          title: "Overview",
          content:
            "Swiss Lake is a pool of capital belonging to individual investors seeking halal, outstanding quarterly profits through open-ended agreements.",
        },
        {
          label: "Vision",
          title: "Our Vision",
          content:
            "To create an investment ecosystem that fosters growth, innovation, and sustainability, ultimately becoming a trusted leader in the investment community.",
        },
        {
          label: "Goals",
          title: "Our Goals",
          content:
            "To empower entrepreneurs and startups through strategic partnerships, providing them with the resources they need to thrive in a competitive landscape.",
        },
        {
          label: "Hotel Investment",
          title: "Investment in Hospitality",
          content: {
            main: "Hotel investment provides one of the most stable, convenient, and outstanding quarterly long-term share profit regarding any other investment instrument that may be compatible with the portfolio of many investors. Also provides an ideal solution to the most puzzling equation:",
            equation:
              "(Maximum Stability + Minimum Risk + Distinctive Long Term Share Profit)",
          },
        },
        {
          label: "Capsule Hotel Concept",
          title: "Redefining Travel",
          content:
            "Capsules are the new and smart way to sleep in a city based on a pioneering idea from Japan, they are the eco-friendly answer to overcrowded and expensive city centers.Capsule hotel concept is the answer for the modern green travellers on a low to moderate budget.",
        },
        {
          label: "Geneva Capsule Hotel",
          title: "Experience in Geneva",
          content:
            "Our Geneva capsule hotel offers modern, eco-friendly accommodation in the heart of the city, providing guests with convenient access to local attractions at affordable rates.",
        },
        // {
        //   label: "Partners",
        //   title: "invest in Experience",
        //   content:
        //     "The capsule hotel concept presents a unique solution for modern travelers, combining affordability with eco-conscious design to meet the needs of a diverse clientele.",
        // },
      ],
    };
  },
  methods: {
    setActiveTab(index) {
      this.activeTab = index;
    },
  },
};
</script>

<style scoped>
.highlight-equation {
  color: #e67e22; /* Set a unique color */
  font-weight: bold; /* Make it stand out */
}
.section {
  padding: 40px 20px;
}

.container {
  max-width: 1200px;
  margin: 0 auto;
}

.tabs {
  display: flex;
  background-color: #4a90e2;
  border-radius: 8px;
  overflow: hidden;
  margin-bottom: 20px;
}

.tab {
  flex: 1;
  padding: 15px;
  text-align: center;
  color: #fff;
  font-weight: 500;
  cursor: pointer;
  transition: background 0.4s, color 0.4s;
}

.tab.active {
  background: #ffffff;
  color: #4a90e2;
  font-weight: 700;
}

.tab:hover {
  background: #3c7ac5;
}

.tab-content {
  padding: 20px;
  background: #fff;
  border-radius: 8px;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);
  animation: fadeIn 0.5s;
}

@keyframes fadeIn {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}

.about-us-section {
  display: flex;
  align-items: center;
  justify-content: space-between;
  margin: 20px auto; /* Reduced margin and centered */
  padding: 20px;
  border-radius: 10px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  max-width: 600px; /* Limit the width to make it smaller */
  background-color: #2947a9; /* Light background color for contrast */
}

.about-content {
  padding: 15px;
  /* background-color: #2947a9; */
  color: white;
  border-radius: 0 10px 10px 0;
  width: 60%; /* Adjusted for a balanced layout */
  font-size: 0.9rem; /* Make text a bit smaller */
}

.about-image {
  width: 80px;
  height: 80px;
  border-radius: 10px; /* Slightly rounded for a modern look */
  object-fit: cover;
  margin-right: 15px; /* Space between image and text */
}

@media (max-width: 768px) {
  .about-us-section {
    flex-direction: column;
    align-items: center;
  }

  .about-content {
    width: 100%;
    text-align: center;
    padding: 20px;
  }

  .about-image {
    width: 100px;
    height: 100px;
  }
  .container {
    max-width: 1200px;
    margin: 0 auto;
  }

  .tabs {
    display: flex;
    background-color: #4a90e2;
    border-radius: 8px;
    overflow-x: auto; /* Enable horizontal scroll */
    margin-bottom: 20px;
    scrollbar-width: none; /* Hide scrollbar for Firefox */
  }

  .tabs::-webkit-scrollbar {
    display: none; /* Hide scrollbar for WebKit browsers */
  }

  .tab {
    flex: 0 0 auto; /* Ensure tabs keep their width */
    padding: 15px;
    text-align: center;
    color: #fff;
    font-weight: 500;
    cursor: pointer;
    transition: background 0.4s, color 0.4s;
  }

  .tab.active {
    background: #ffffff;
    color: #4a90e2;
    font-weight: 700;
  }

  .tab:hover {
    background: #3c7ac5;
  }

  .tab-content {
    padding: 20px;
    background: #fff;
    border-radius: 8px;
    box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);
    animation: fadeIn 0.5s;
  }

  @keyframes fadeIn {
    from {
      opacity: 0;
    }
    to {
      opacity: 1;
    }
  }

  @media (max-width: 768px) {
    .about-us-section {
      flex-direction: column;
      align-items: center;
      padding: 15px;
    }

    .about-content {
      width: 100%;
      text-align: center;
      padding: 15px;
      border-radius: 10px;
    }

    .about-image {
      margin-bottom: 10px;
    }
    .tabs {
      padding: 10px 0; /* Add some padding for better mobile view */
    }

    .tab {
      padding: 10px 12px; /* Decrease padding to fit more tabs in view */
      font-size: 0.9rem; /* Make font size smaller for mobile */
      flex-shrink: 0; /* Prevent shrinking of tabs */
    }

    .tab-content {
      padding: 15px; /* Adjust content padding for smaller screens */
    }
  }
}
</style>
