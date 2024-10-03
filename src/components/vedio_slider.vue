<template>
  <swiper
    ref="mySwiper"
    :modules="[Navigation]"
    :navigation="{
      nextEl: '.swiper-button-next',
      prevEl: '.swiper-button-prev',
    }"
    @slideChangeTransitionStart="onTransitionStart"
    @slideChangeTransitionEnd="onTransitionEnd"
  >
    <swiper-slide v-for="(videoSrc, index) in videoSources" :key="index">
      <video :src="videoSrc" muted preload="none" ref="videos"></video>
    </swiper-slide>
  </swiper>
  <div class="swiper-button-prev"></div>
  <div class="swiper-button-next"></div>
</template>

<script>
import { Swiper, SwiperSlide } from "swiper/vue";
import "swiper/swiper-bundle.min.css";

export default {
  components: {
    Swiper,
    SwiperSlide,
  },
  data() {
    return {
      videoSources: [
        "https://into-the-program.com/uploads/sample_video01.mp4",
        "https://into-the-program.com/uploads/sample_video02.mp4",
        "https://into-the-program.com/uploads/sample_video03.mp4",
      ],
    };
  },
  methods: {
    onTransitionStart() {
      this.$refs.videos.forEach((video) => {
        video.pause();
      });
    },
    onTransitionEnd() {
      const activeIndex = this.$refs.mySwiper.swiper.activeIndex;
      const activeVideo = this.$refs.videos[activeIndex];
      if (activeVideo) {
        activeVideo.play();
      }
    },
  },
};
</script>

<style scoped>
.swiper-container {
  width: 100%;
  height: 100vh;
  max-width: 940px;
  margin: 0 auto;
}

.swiper-slide video {
  width: 100%;
  height: 100%;
}
.swiper-button-prev,
.swiper-button-next {
  color: #fff; /* Adjust button color as needed */
}
</style>
