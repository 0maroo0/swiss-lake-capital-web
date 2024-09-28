<template>
  <section id="home" class="section">
    <div class="home">
      <img alt="Vue logo" src="../assets/ZurichOverview.jpeg" />
      <div class="overlay">
        <h1>Building things is our mission</h1>
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
  position: relative;
  width: 100%;
  height: 100vh; /* Make it full viewport height */
  display: flex;
  justify-content: center;
  align-items: center;
  margin: 0; /* Remove any default margin */
  padding: 0; /* Remove any default padding */
}
.home img {
  width: 100%;
  height: 90vh; /* Make it cover the full height */
  object-fit: cover; /* Make sure the image covers the container */
  margin: 0; /* Remove any default margin */
  padding: 0; /* Remove any default padding */
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
  padding: 20px 40px; /* Add padding for better text appearance */
  border-radius: 10px; /* Rounded corners for modern look */
  text-align: center;
}

.overlay h1 {
  margin: 0;
  font-size: 75px; /* Adjust the font size */
  font-weight: bold;
  color: #333; /* Dark color for contrast */
  font-family: "Poppins", sans-serif; /* Use a modern font */
}
</style>
