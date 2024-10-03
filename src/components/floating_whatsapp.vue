<template>
  <div class="whatsapp-fab">
    <a
      href="https://wa.me/+201065840930"
      target="_blank"
      rel="noopener noreferrer"
    >
      <img
        src="https://upload.wikimedia.org/wikipedia/commons/6/6b/WhatsApp.svg"
        alt="WhatsApp"
      />
    </a>
  </div>
</template>

<script>
export default {
  name: "WhatsAppFAB",
};
</script>

<style scoped>
.whatsapp-fab {
  position: fixed;
  bottom: 20px;
  right: 20px;
  width: 60px;
  height: 60px;
  background-color: #25d366;
  border-radius: 50%;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
  display: flex;
  justify-content: center;
  align-items: center;
  cursor: pointer;
  z-index: 1000;
}

.whatsapp-fab img {
  width: 35px;
  height: 35px;
}
</style>
