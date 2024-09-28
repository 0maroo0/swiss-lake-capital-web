<template>
  <div class="contact_with_number">
    <img alt="Vue logo" src="../assets/rewsr1.png" />
    <div class="overlay consultation-section">
      <div class="consultation-text">
        <h2 class="section-title">
          Free consultation with exceptional quality
        </h2>
        <p class="section-body">Just one call away: +84 1102 2703</p>
      </div>
      <button class="consultation-button">Get your consultation</button>
    </div>
  </div>
</template>

<script>
export default {
  name: "contact_with_number",
};
</script>

<style scoped>
.contact_with_number {
  position: relative;
  width: 100%;
  height: 40vh; /* Adjust the height as needed */
  display: flex;
  justify-content: center;
  align-items: center;
  margin: 0; /* Remove any default margin */
  padding: 0; /* Remove any default padding */
}

.contact_with_number img {
  width: 100%;
  height: 100%; /* Cover the full height */
  object-fit: cover; /* Make sure the image covers the container */
  filter: brightness(70%); /* Darken the image for better text contrast */
}

.overlay {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  display: flex;
  flex-direction: row;
  align-items: center; /* Center vertically */
  justify-content: space-between; /* Space between text and button */
  background-color: rgba(
    255,
    255,
    255,
    0.8
  ); /* White background with opacity */
  padding: 20px 40px; /* Add padding for better appearance */
  border-radius: 10px; /* Rounded corners for modern look */
}

.consultation-text {
  max-width: 70%; /* Limit the width for the text */
}

.section-title {
  font-size: 1.8em; /* Larger font size for title */
  color: #333; /* Dark color for title */
  margin-bottom: 5px; /* Space between title and body */
  font-weight: bold; /* Make title bold */
}

.section-body {
  font-size: 1.2em; /* Slightly smaller font for body */
  color: #555; /* Medium-dark color for body text */
}

.consultation-button {
  all: unset;
  width: 180px;
  height: 50px;
  font-size: 16px;
  background-color: #2947a9;
  color: #fff;
  border: none;
  border-radius: 5px;
  padding: 10px 20px;
  cursor: pointer;
  text-align: center;
  transition: background-color 0.3s, transform 0.2s;
}

.consultation-button:hover {
  background-color: #1f3b8a; /* Darker color on hover */
  transform: scale(1.05); /* Slightly enlarge button on hover */
}

.consultation-button:active {
  transform: scale(0.98); /* Slightly shrink on click */
}
</style>
