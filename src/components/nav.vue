<template>
  <nav class="navbar">
    <div class="logo">
      <img src="../assets/logo-swiss.png" />
    </div>
    <div class="nav-links" :class="{ active: isMenuOpen }">
      <a href="#home" @click="closeMenu">Home</a>
      <a href="#services" @click="closeMenu">Investment Calculator</a>
      <a href="#meet" @click="closeMenu">scheduling meet</a>
      <a href="#contact" @click="closeMenu">Contact Us</a>
    </div>
    <h1 class="logo-swiss">
      <span class="color1">Swiss</span>
      <span class="color2"> lake</span>
      <span class="color3"> capital</span>
    </h1>
    <button class="menu-toggle" @click="toggleMenu">
      <span class="bar"></span>
      <span class="bar"></span>
      <span class="bar"></span>
    </button>
  </nav>
</template>

<script>
export default {
  name: "NavBar",
  data() {
    return {
      isMenuOpen: false,
    };
  },
  methods: {
    toggleMenu() {
      this.isMenuOpen = !this.isMenuOpen;
    },
    closeMenu() {
      if (window.innerWidth <= 768) {
        this.isMenuOpen = false;
      }
    },
  },
};
</script>
<style scoped>
.logo-swiss {
  font-family: "Inconsolata", monospace;
  font-weight: bold;
  letter-spacing: 2px;
}
.color1 {
  font-size: 35px;
  color: #f9995d; /* Orange color */
}

.color2 {
  font-size: 35px;

  color: #2947a9; /* Blue color */
}

.color3 {
  font-size: 35px;

  color: green; /* Green color */
}

img {
  height: 150px; /* Reduced logo height */
  width: 150px; /* Reduced logo width */
}

.navbar {
  display: flex;
  justify-content: space-between;
  align-items: center;
  position: fixed;
  top: 0;
  width: 100%;
  padding: 5px 10px; /* Reduced padding */
  background-color: #ffffff;
  box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1); /* Slightly more prominent shadow */
  z-index: 1000;
}

.logo h3 {
  margin: 0;
  font-family: "Poppins", sans-serif; /* Modern font style */
  font-size: 1.2rem; /* Reduced font size */
  color: #f9995d; /* Logo color matching hover effect */
}

.nav-links {
  display: flex;
  gap: 15px; /* Reduced gap for better spacing */
}

.nav-links a {
  text-decoration: none;
  font-weight: bold;
  color: #2c3e50;
  font-family: "Poppins", sans-serif; /* Modern font style */
  font-size: 0.9rem; /* Adjusted font size for better readability */
  transition: color 0.3s ease, transform 0.3s ease; /* Smooth transition */
}

.nav-links a:hover {
  color: #f9995d; /* Highlight color for hover */
  transform: scale(1.05); /* Slight scaling effect on hover */
}

.nav-links a:active {
  transform: scale(0.95); /* Subtle shrinking effect when clicked */
}

/* Mobile Styles */
@media (max-width: 768px) {
  img {
    height: 100px; /* Reduced logo height */
    width: 100px; /* Reduced logo width */
  }
  .color1,
  .color2,
  .color3 {
    font-size: 20px; /* Reduced font size for mobile */
  }
  .nav-links {
    display: none; /* Hide links by default */
    flex-direction: column; /* Stack links vertically */
    position: absolute;
    top: 50px; /* Position below navbar */
    left: 0;
    width: 100%;
    background-color: #ffffff; /* Background color for mobile menu */
    box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1); /* Shadow for dropdown */
    padding: 10px 0; /* Padding for links */
  }

  .nav-links.active {
    display: flex; /* Show links when menu is open */
  }

  .menu-toggle {
    margin: 20px; /* Reduced margin for the menu toggle */
    display: flex;
    flex-direction: column;
    cursor: pointer;
  }

  .menu-toggle .bar {
    height: 2px; /* Reduced height for the menu bars */
    width: 25px;
    background-color: #2c3e50; /* Color of the menu bars */
    margin: 3px 0; /* Spacing between bars */
  }
}
</style>
