<template>
  <section id="media" class="section">
    <div class="gallery-container">
      <div class="selected-image">
        <img :src="selectedPhoto" alt="Selected Photo" />
      </div>
      <div class="thumbnails-container">
        <div class="thumbnails">
          <div
            v-for="(photo, index) in photos"
            :key="index"
            class="thumbnail"
            :class="{ active: selectedPhoto === photo }"
            @click="selectPhoto(photo)"
          >
            <img :src="photo" alt="Thumbnail" />
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  // eslint-disable-next-line vue/multi-word-component-names
  name: "Slider",
  data() {
    return {
      photos: [
        "https://greenmarmot.com/images/capsules/3_Kapselhotel.jpg",
        "https://greenmarmot.com/images/capsules/7_Kapselhotel.jpg",
        "https://greenmarmot.com/images/capsules/10_Kapselhotel.jpg",
        "https://greenmarmot.com/images/capsules/14_Kapselhotel.jpg",
        "https://greenmarmot.com/images/capsules/61_Kapselhotel.jpg",
        "https://greenmarmot.com/images/capsules/62_Kapselhotel.jpg",
        "https://greenmarmot.com/images/capsules/double_capsule1.jpg",
        "https://greenmarmot.com/images/capsules/double_capsule2.jpg",
        "https://greenmarmot.com/images/capsules/double_capsule3.jpg",
        "https://greenmarmot.com/images/capsules/single_capsule.jpg",
        "https://greenmarmot.com/images/capsules/11_Kapselhotel.jpg",
        "https://greenmarmot.com/images/capsules/reception.jpg",
        "https://greenmarmot.com/images/capsules/13_Kapselhotel.jpg",
        "https://greenmarmot.com/images/capsules/9_Kapselhotel.jpg",
        "https://greenmarmot.com/images/capsules/8_Kapselhotel.jpg",
        "https://greenmarmot.com/images/capsules/6_Kapselhotel.jpg",
        "https://greenmarmot.com/images/capsules/5_Kapselhotel.jpg",
      ],
      selectedPhoto:
        "https://greenmarmot.com/images/capsules/3_Kapselhotel.jpg",
    };
  },
  methods: {
    selectPhoto(photo) {
      this.selectedPhoto = photo;
    },
  },
};
</script>

<style scoped>
.gallery-container {
  display: flex;
  width: 100%;
  gap: 10px;
  max-width: 1000px;
  margin: 20px auto;
  flex-wrap: wrap; /* Allow items to wrap */
}

.intro-text {
  text-align: center;
  margin-bottom: 20px;
}

.intro-text h2 {
  font-size: 2rem;
  margin-bottom: 10px;
  color: #333;
}

.intro-text p {
  font-size: 1.1rem;
  line-height: 1.5;
  color: #666;
  max-width: 800px;
  margin: 0 auto;
}

.selected-image {
  flex: 4;
  max-width: 80%;
  min-width: 300px; /* Set minimum width for mobile */
}

.selected-image img {
  width: 100%;
  height: 500px; /* Maintain aspect ratio */
  border-radius: 10px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
}

.thumbnails-container {
  flex: 1;
  max-width: 20%;
  height: 500px;
  overflow-y: auto;
  padding: 5px;
  border-radius: 5px;
  border: 1px solid #ddd;
}

.thumbnails {
  display: flex;
  flex-direction: column;
  gap: 10px;
}

.thumbnail {
  cursor: pointer;
  transition: transform 0.2s ease;
}

.thumbnail img {
  width: 100%;
  height: auto;
  border-radius: 5px;
}

.thumbnail.active {
  transform: scale(1.05);
  border: 2px solid #007bff;
}

.thumbnail:hover {
  transform: scale(1.05);
}

/* Mobile responsive styles */
@media (max-width: 768px) {
  .gallery-container {
    display: flex;
    flex-direction: column; /* Stack vertically on smaller screens */
    align-items: center; /* Center items horizontally */
    padding: 10px; /* Add padding around the container */
  }

  .selected-image {
    max-width: 100%; /* Full width on mobile */
    height: auto; /* Allow height to adjust */
    margin-bottom: 10px; /* Space below the selected image */
  }

  .thumbnails-container {
    display: flex; /* Ensure the container is a flexbox */
    max-width: 100%; /* Full width for thumbnails */
    overflow-x: auto; /* Allow horizontal scrolling for thumbnails */
    padding: 10px 0; /* Add padding for aesthetics */
  }

  .thumbnails {
    height: 40px;
    display: flex; /* Ensure thumbnails are displayed in a row */
    flex-direction: row; /* Display thumbnails in a row */
    overflow-x: auto; /* Allow horizontal scrolling for thumbnails */
    padding: 5px 0; /* Add padding for aesthetics */
  }

  .thumbnail {
    flex: 0 0 auto; /* Prevent flex items from shrinking */
    width: 70px; /* Set a fixed width for thumbnails on mobile */
    margin-right: 10px; /* Space between thumbnails */
  }

  .thumbnail img {
    width: 100%; /* Ensure the image fills the thumbnail */
    height: auto; /* Maintain aspect ratio */
    border-radius: 5px; /* Rounded corners */
  }

  .selected-image img {
    width: 100%; /* Full width for selected image */
    height: auto; /* Maintain aspect ratio */
    max-height: 300px; /* Set a max height to control dimensions */
    border-radius: 10px; /* Maintain border radius */
    object-fit: cover; /* Crop the image to fill the space */
  }
}
</style>
