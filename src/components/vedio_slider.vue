<template>
  <section id="review">
    <h2>Video Review</h2>
    <div class="video-slider">
      <!-- <button @click="prevSlide" class="nav-button prev-button">Prev</button> -->

      <div class="video-wrapper">
        <video
          v-for="(video, index) in videos"
          :key="index"
          :src="video"
          preload="none"
          muted
          ref="videoElements"
          :class="{ active: currentIndex === index }"
          @canplay="onCanPlay"
        ></video>
      </div>
      <!-- <button @click="nextSlide" class="nav-button next-button">Next</button> -->
    </div>
  </section>
</template>

<script>
export default {
  data() {
    return {
      videos: [
        "http://swisslakecapital.com/assets/review_hotelmp4",
        // "http://swisslakecapital.com/assets/v1.mp4",
      ],
      currentIndex: 0,
    };
  },
  mounted() {
    this.playCurrentVideo();
  },
  methods: {
    prevSlide() {
      this.pauseCurrentVideo();
      this.currentIndex =
        (this.currentIndex - 1 + this.videos.length) % this.videos.length;
      this.playCurrentVideo();
    },
    nextSlide() {
      this.pauseCurrentVideo();
      this.currentIndex = (this.currentIndex + 1) % this.videos.length;
      this.playCurrentVideo();
    },
    pauseCurrentVideo() {
      const videoElements = this.$refs.videoElements;
      if (videoElements[this.currentIndex]) {
        videoElements[this.currentIndex].pause();
      }
    },
    playCurrentVideo() {
      const videoElements = this.$refs.videoElements;
      if (videoElements[this.currentIndex]) {
        videoElements[this.currentIndex].play();
      }
    },
    onCanPlay(event) {
      if (event.target.classList.contains("active")) {
        event.target.play();
      }
    },
  },
};
</script>

<style scoped>
.video-slider {
  display: flex;
  align-items: center;
  justify-content: space-between;
  width: 100%;
  max-width: 940px;
  margin: 0 auto;
  height: 80vh;
}

.video-wrapper {
  width: 100%;
  display: flex;
  overflow: hidden;
  position: relative;
  height: 100%;
}

video {
  width: 100%;
  height: 100%;
  position: absolute;
  left: 100%;
  transition: left 0.5s ease;
  opacity: 0;
}

video.active {
  left: 0;
  opacity: 1;
}

.nav-button {
  background-color: #333;
  color: #fff;
  border: none;
  padding: 5px 10px;
  cursor: pointer;
  z-index: 2;
}

.prev-button {
  margin-right: 5px;
}

.next-button {
  margin-left: 5px;
}

/* Mobile Responsive Styles */
@media (max-width: 768px) {
  .video-slider {
    flex-direction: column;
    height: 50vh; /* Reduce height for mobile */
  }

  .nav-button {
    padding: 5px;
    margin: 5px 0;
  }

  .video-wrapper {
    height: 100%;
  }

  video {
    position: relative;
    left: 100%;
  }

  video.active {
    left: 0;
  }
}
</style>
