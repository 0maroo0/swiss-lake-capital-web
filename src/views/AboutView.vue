<template>
  <section id="about" class="section">
    <div class="about">
      <h2>Our Reputation</h2>
      <div class="cards-container">
        <div class="card">
          <div class="icon">
            <img src="../assets/icon1.png" alt="Icon 1" />
          </div>
          <h3>Quality Service</h3>
          <p>
            We provide high-quality services to meet your needs and exceed
            expectations.
          </p>
        </div>
        <div class="card">
          <div class="icon">
            <img src="../assets/icon1.png" alt="Icon 2" />
          </div>
          <h3>Reliability</h3>
          <p>
            Our commitment to reliability ensures that you can trust us to time.
          </p>
        </div>
        <div class="card">
          <div class="icon">
            <img src="../assets/icon1.png" alt="Icon 3" />
          </div>
          <h3>Customer Satisfaction</h3>
          <p>
            We prioritize customer satisfaction to build lasting relationships.
          </p>
        </div>
      </div>
    </div>
  </section>
  <div class="about-us-section">
    <div class="about-content">
      <h2>About Us</h2>
      <p>
        For more than 30 years we have been delivering world-class construction
        built many lasting relationships along the way. For more than 30 years
        we have been delivering world-class construction built many lasting
        relationships along the way. For more than 30 years we have been
        delivering world-class construction built many lasting relationships
        along the way.
      </p>
    </div>
    <img
      src="../assets/unsplash.png"
      alt="Construction Image"
      class="about-image"
    />
  </div>
</template>
<script>
export default {
  name: "ReputationSection",
};
</script>

<style scoped>
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

.card p {
  color: #666;
  font-size: 1rem;
}

.about-us-section {
  position: relative;
  display: flex;
  align-items: center;
  flex-direction: row;
  width: 100%;
  height: 500px;
  overflow: hidden;
}

.about-content {
  position: absolute;
  right: 0;
  width: 30%;
  height: 60%;
  background-color: #2947a9; /* Blue background */
  color: white;
  padding: 30px;
  margin-right: 190px;
  text-align: start;
  z-index: 10;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
}

.about-content h2 {
  font-family: "Poppins", sans-serif;
  font-size: 2.5rem;
  margin-bottom: 20px;
}

.about-content p {
  font-family: "Poppins", sans-serif;
  font-size: 1rem;
  line-height: 1.6;
}

.about-image {
  width: 50%;
  height: 100%;
  padding-left: 90px;
  object-fit: cover;
  object-position: left; /* Focus on the left side of the image */
}

@media (max-width: 768px) {
  .cards-container {
    flex-direction: column;
    gap: 20px;
  }

  .card {
    width: 90%;
    margin: 0 auto;
  }

  .about-us-section {
    flex-direction: column;
    height: auto;
  }

  .about-content {
    position: static;
    width: 100%;
    height: auto;
    margin-bottom: 20px;
    padding: 20px;
  }

  .about-image {
    width: 100%;
    height: auto;
  }
}
</style>
