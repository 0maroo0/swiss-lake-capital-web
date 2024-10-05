<template>
  <section id="home" class="section">
    <div class="home">
      <img alt="Zurich Overview" src="../assets/ZurichOverview.jpeg" />
      <div class="overlay">
        <h1>your trust is our commitment</h1>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: "HomeView",
  components: {},
};
</script>

<style scoped>
.home {
  margin-top: 50px; /* Maintain margin at the top */
  position: relative;
  width: 100%;
  height: 100vh; /* Full viewport height */
  display: flex;
  justify-content: center;
  align-items: center;
  margin: 0;
  padding: 0;
}

.home img {
  width: 100%;
  height: 90vh; /* Cover the full height */
  object-fit: cover; /* Make sure the image covers the container */
  filter: brightness(70%); /* Darken the image for better text contrast */
}

.overlay {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  background-color: rgba(
    255,
    255,
    255,
    0.5
  ); /* White background with opacity */
  padding: 20px 40px; /* Padding for text appearance */
  border-radius: 10px; /* Rounded corners */
  text-align: center;
}

.overlay h1 {
  margin: 0;
  font-size: 60px; /* Large font size */
  font-weight: bold;
  color: #333; /* Dark color for contrast */
  font-family: "Poppins", sans-serif; /* Modern font */
}

/* Mobile responsive styles */
@media (max-width: 768px) {
  .home {
    height: auto; /* Allow height to adjust */
  }

  .home img {
    height: 50vh; /* Adjust image height for mobile */
  }

  .overlay {
    padding: 10px 20px; /* Less padding for mobile */
  }

  .overlay h1 {
    font-size: 30px; /* Smaller font size for mobile */
    line-height: 1.2; /* Adjust line height for better readability */
  }
}

/* Added margin for the section below the navbar */
.section {
  padding-top: 70px; /* Ensure this matches the height of the navbar */
}
</style>
