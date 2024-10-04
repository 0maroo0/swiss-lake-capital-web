<template>
  <div class="calendly-iframe-container">
    <iframe
      src="https://calendly.com/zeyadabdelaziz-swisslakecapital"
      width="100%"
      height="600"
      frameborder="0"
      scrolling="no"
      allowtransparency="true"
    ></iframe>
  </div>
</template>

<script>
export default {
  name: "CalendlyIframe",
};
</script>

<style scoped>
.calendly-iframe-container {
  width: 100%;
  height: 600px; /* Adjust height as needed */
  max-width: 800px; /* Adjust max-width as desired */
  margin: 0 auto; /* Center the iframe horizontally */
}
</style>
