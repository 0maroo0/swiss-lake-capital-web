<template>
  <div class="contact_with_number">
    <img alt="Vue logo" src="../assets/rewsr1.png" />
    <div class="overlay consultation-section">
      <div class="consultation-text">
        <h2 class="section-title">
          Free consultation with exceptional quality
        </h2>
        <p class="section-body">Just one call away: +20 1065840930</p>
      </div>
      <button class="consultation-button" @click="openDialog">
        Meet With us
      </button>
    </div>
  </div>

  <!-- Modal Dialog -->
  <div v-if="showMeeting" class="modal">
    <div class="modal-content">
      <span class="close-button" @click="closeDialog">&times;</span>
      <Meeting />
    </div>
  </div>
</template>

<script>
import Meeting from "@/components/meeting.vue";

export default {
  name: "contact_with_number",
  components: {
    Meeting,
  },
  data() {
    return {
      showMeeting: false,
    };
  },
  methods: {
    openDialog() {
      this.showMeeting = true;
    },
    closeDialog() {
      this.showMeeting = false;
    },
  },
};
</script>

<style scoped>
.contact_with_number {
  position: relative;
  width: 100%;
  height: 40vh;
  display: flex;
  justify-content: center;
  align-items: center;
  margin: 0;
  padding: 0;
}

.contact_with_number img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  filter: brightness(70%);
}

.overlay {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: space-between;
  background-color: rgba(255, 255, 255, 0.8);
  padding: 20px 40px;
  border-radius: 10px;
}

.consultation-text {
  max-width: 70%;
}

.section-title {
  font-size: 1.8em;
  color: #333;
  margin-bottom: 5px;
  font-weight: bold;
}

.section-body {
  font-size: 1.2em;
  color: #555;
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
  background-color: #1f3b8a;
  transform: scale(1.05);
}

.consultation-button:active {
  transform: scale(0.98);
}

/* Modal Styles */
.modal {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.5);
  display: flex;
  justify-content: center;
  align-items: center;
  z-index: 1000;
}

.modal-content {
  background-color: #fff;
  padding: 20px;
  border-radius: 10px;
  width: 90%;
  max-width: 600px;
  position: relative;
}

.close-button {
  position: absolute;
  top: 10px;
  right: 10px;
  font-size: 24px;
  cursor: pointer;
}

@media (max-width: 768px) {
  .contact_with_number {
    height: 250px;
  }

  .overlay {
    padding: 15px;
  }

  .section-title {
    font-size: 1.4em;
  }

  .section-body {
    font-size: 0.9em;
  }
}
</style>
