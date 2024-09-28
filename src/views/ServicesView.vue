<template>
  <section id="services" class="section">
    <div class="services">
      <h2>Services</h2>
      <div class="cards-container">
        <div class="card">
          <div class="icon">
            <img src="../assets/icon.png" alt="Icon 1" />
          </div>
          <h3>Quality Service</h3>
          <hr />
          <p>
            We provide high-quality services to meet your needs and exceed
            expectations.
          </p>
        </div>
        <div class="card">
          <div class="icon">
            <img src="../assets/icon2.png" alt="Icon 2" />
          </div>
          <h3>Reliability</h3>
          <hr />
          <p>
            Our commitment to reliability ensures that you can trust us to time.
          </p>
        </div>
        <div class="card">
          <div class="icon">
            <img src="../assets/icon.png" alt="Icon 3" />
          </div>
          <h3>Customer Satisfaction</h3>
          <hr />
          <p>
            We prioritize customer satisfaction to build lasting relationships.
          </p>
        </div>
        <div class="card">
          <div class="icon">
            <img src="../assets/icon.png" alt="Icon 1" />
          </div>
          <h3>Quality Service</h3>
          <hr />
          <p>
            We provide high-quality services to meet your needs and exceed
            expectations.
          </p>
        </div>
        <div class="card">
          <div class="icon">
            <img src="../assets/icon2.png" alt="Icon 2" />
          </div>
          <h3>Reliability</h3>
          <hr />
          <p>
            Our commitment to reliability ensures that you can trust us to time.
          </p>
        </div>
        <div class="card">
          <div class="icon">
            <img src="../assets/icon.png" alt="Icon 3" />
          </div>
          <h3>Customer Satisfaction</h3>
          <hr />
          <p>
            We prioritize customer satisfaction to build lasting relationships.
          </p>
        </div>
      </div>
    </div>
    <OurNumber />
    <ContactWithNumber />
    <Slider />
  </section>
</template>
<script>
import OurNumber from "@/components/ourNumber.vue";
import ContactWithNumber from "@/components/contact_with_number.vue";
import Slider from "@/components/slider.vue";
export default {
  // eslint-disable-next-line vue/multi-word-component-names
  name: "section",
  components: {
    OurNumber,
    // eslint-disable-next-line vue/no-unused-components
    ContactWithNumber,
    Slider,
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
  gap: 20px;
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
</style>
