<template>
  <h2 class="contact-us">Review</h2>
  <div class="testimonial-slider">
    <button @click="prevSlide" class="nav-button left">&lt;</button>

    <div class="testimonial-container">
      <div
        class="testimonial"
        v-for="(testimonial, index) in visibleTestimonials"
        :key="index"
      >
        <blockquote>
          {{ testimonial.quote }}
          <div class="arrow"></div>
        </blockquote>
        <img :src="testimonial.image" alt="testimonial" />
        <div class="author">
          <h5>
            {{ testimonial.author }} <span>{{ testimonial.source }}</span>
          </h5>
        </div>
      </div>
    </div>

    <button @click="nextSlide" class="nav-button right">&gt;</button>
  </div>
</template>

<script>
export default {
  name: "TestimonialSlider",
  data() {
    return {
      testimonials: [
        {
          quote:
            "Calvin: You know sometimes when I'm talking, my words can't keep up with my thoughts... I wonder why we think faster than we speak.",
          image:
            "https://s3-us-west-2.amazonaws.com/s.cdpn.io/331810/sq-sample3.jpg",
          author: "Calvin",
          source: "LittleSnippets.net",
        },
        {
          quote:
            "Thank you. Before I begin, I'd like everyone to notice that my report is in a professional, clear plastic binder...",
          image:
            "https://s3-us-west-2.amazonaws.com/s.cdpn.io/331810/sq-sample27.jpg",
          author: "Max Conversion",
          source: "LittleSnippets.net",
        },
        {
          quote:
            "My behaviour is addictive functioning in a disease process of toxic co-dependency...",
          image:
            "https://s3-us-west-2.amazonaws.com/s.cdpn.io/331810/sq-sample17.jpg",
          author: "Eleanor Faint",
          source: "LittleSnippets.net",
        },
        // More testimonials can be added here...
      ],
      currentSlide: 0,
      slidesToShow: 1, // Show one testimonial at a time on mobile
    };
  },
  computed: {
    visibleTestimonials() {
      return this.testimonials.slice(
        this.currentSlide,
        this.currentSlide + this.slidesToShow
      );
    },
  },
  methods: {
    nextSlide() {
      if (this.currentSlide < this.testimonials.length - this.slidesToShow) {
        this.currentSlide++;
      } else {
        this.currentSlide = 0; // Loop back to the start
      }
    },
    prevSlide() {
      if (this.currentSlide > 0) {
        this.currentSlide--;
      } else {
        this.currentSlide = this.testimonials.length - this.slidesToShow; // Loop to the end
      }
    },
  },
};
</script>

<style scoped>
.testimonial-slider {
  display: flex;
  align-items: center;
  justify-content: center;
  position: relative;
  max-width: 1200px;
  margin: auto;
  padding: 20px; /* Add padding for spacing */
}

.testimonial-container {
  display: flex;
  transition: transform 0.5s ease;
}

.testimonial {
  background-color: #fafafa;
  padding: 25px;
  border-radius: 8px;
  margin: 0 10px;
  flex: 1;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
}

blockquote {
  font-style: italic;
  margin: 0 0 10px 0;
}

img {
  width: 90px;
  height: 90px;
  border-radius: 50%;
  margin: 10px 0;
  object-fit: cover; /* Maintain aspect ratio */
}

.author {
  font-weight: bold;
  text-align: center;
}

.nav-button {
  background: none;
  border: none;
  font-size: 2em;
  cursor: pointer;
  z-index: 1;
  color: #007bff; /* Color for buttons */
  transition: color 0.3s; /* Transition for hover effect */
}

.nav-button:hover {
  color: #0056b3; /* Darker color on hover */
}

.nav-button.left {
  position: absolute;
  left: 10px;
}

.nav-button.right {
  position: absolute;
  right: 10px;
}

/* Responsive Styles */
@media (max-width: 768px) {
  .testimonial-slider {
    flex-direction: column; /* Stack vertically on mobile */
    padding: 10px; /* Reduce padding on mobile */
  }

  .nav-button {
    font-size: 1.5em; /* Smaller buttons */
  }

  .testimonial {
    min-width: 100%; /* Full width on mobile */
    margin: 10px 0; /* Margin adjustment */
    box-shadow: none; /* Remove shadow for mobile */
  }
}

@media (max-width: 480px) {
  .testimonial {
    padding: 15px; /* Adjust padding for smaller screens */
  }
}
</style>
