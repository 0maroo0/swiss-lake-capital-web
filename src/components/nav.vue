<template>
  <nav class="navbar">
    <div class="logo">
      <img src="../assets/logo-swiss.png" />
    </div>
    <div class="nav-links">
      <a href="#home">Home</a>
      <a href="#about">About Us</a>
      <a href="#services">Our Services</a>
      <a href="#contact">Contact Us</a>
    </div>
  </nav>
</template>

<script>
export default {
  name: "NavBar",
};
</script>

<style scoped>
img {
  height: 100px;
  width: 100px;
}
.navbar {
  display: flex;
  justify-content: space-around;
  align-items: center;
  position: fixed;
  top: 0;
  width: 100%;
  padding: 5px 10px; /* Increased padding for more breathing room */
  background-color: #ffffff;
  box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1); /* Slightly more prominent shadow */
  z-index: 1000;
}

.logo h3 {
  margin: 0;
  font-family: "Poppins", sans-serif; /* Modern font style */
  font-size: 1.5rem; /* Increased font size */
  color: #f9995d; /* Logo color matching hover effect */
}

.nav-links {
  display: flex;
  gap: 30px; /* Increased gap for better spacing */
}

.nav-links a {
  text-decoration: none;
  font-weight: bold;
  color: #2c3e50;
  font-family: "Poppins", sans-serif; /* Modern font style */
  font-size: 1.1rem; /* Adjusted font size for better readability */
  transition: color 0.3s ease, transform 0.3s ease; /* Smooth transition */
}

.nav-links a:hover {
  color: #f9995d; /* Highlight color for hover */
  transform: scale(1.05); /* Slight scaling effect on hover */
}

.nav-links a:active {
  transform: scale(0.95); /* Subtle shrinking effect when clicked */
}
</style>
