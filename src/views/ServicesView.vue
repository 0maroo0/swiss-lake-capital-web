<template>
  <section id="services" class="section">
    <OurNumber />
    <ContactWithNumber />
  </section>
</template>
<script>
import OurNumber from "@/components/ourNumber.vue";
import ContactWithNumber from "@/components/contact_with_number.vue";
export default {
  // eslint-disable-next-line vue/multi-word-component-names
  name: "section",
  components: {
    OurNumber,
    // eslint-disable-next-line vue/no-unused-components
    ContactWithNumber,
  },
};
</script>

<style scoped>
h2 {
  padding-top: 50px;
}
.about {
  text-align: center;
  padding: 50px 20px;
  background-color: #f9f9f9;
}

.about h2 {
  font-size: 2rem;
  margin-bottom: 30px;
  font-family: "Poppins", sans-serif;
}

.cards-container {
  display: flex;
  justify-content: space-around;
  /* gap: 20px; */
  flex-wrap: wrap;
}

.card {
  background: #ffffff;
  padding: 20px;
  border-radius: 10px;
  box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
  width: 27%;
  min-width: 200px;
  text-align: center;
  transition: transform 0.3s ease-in-out;
}

.card:hover {
  transform: translateY(-10px);
  background-color: #2947a9;
  color: white; /* Change text color to white on hover */
}

.icon img {
  width: 50px;
  height: 50px;
  margin-bottom: 20px;
}

.card h3 {
  font-size: 1.5rem;
  margin-bottom: 15px;
  font-family: "Poppins", sans-serif;
}
.card:hover h3,
.card:hover p {
  /* Change text color on hover */
  color: white; /* White text color on hover */
}

.card p {
  color: #666;
  font-size: 1rem;
}
hr {
  border: 0;
  height: 1px;
  background-color: #ccc; /* Light grey color */
  margin: 20px 0; /* Add spacing around the divider */
}

/* Responsive styles */
@media (max-width: 768px) {
  .cards-container {
    justify-content: center; /* Center cards on small screens */
  }

  .card {
    width: 90%; /* Full width for mobile */
    margin-bottom: 20px; /* Space between cards */
  }

  .about h2 {
    font-size: 1.8rem; /* Smaller font size for mobile */
  }

  h2 {
    padding-top: 30px; /* Adjust padding for mobile */
  }
}

@media (max-width: 480px) {
  .card h3 {
    font-size: 1.3rem; /* Smaller font size for headings on mobile */
  }

  .card p {
    font-size: 0.9rem; /* Smaller font size for paragraphs on mobile */
  }
}
</style>
