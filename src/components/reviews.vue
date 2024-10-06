<template>
  <h2 class="contact-us">greenmarmot Review</h2>
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
            {{ testimonial.author }}
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
            "Everything was fine, clean,hot water in the shower, bed very comfortable.",
          image: "http://swisslakecapital.com/assets/ava-m.png",

          author: "Marilyn",
        },
        {
          quote: "I like it in general",
          image: "http://swisslakecapital.com/assets/ava-n.png",

          author: "Nervin",
        },
        {
          quote:
            "Good value for money,easy to find.Comfy bed,,clean bathroom and kind staff",
          image: "http://swisslakecapital.com/assets/ava-p.png",
          author: "Pavan",
        },
        {
          quote: "Perfect location clean bathroom.",
          image: "http://swisslakecapital.com/assets/ava-p.png",

          author: "Philip",
        },
        {
          quote:
            "Good stay. Recommended for the budget and very much reachable. Good food options nearby",
          image: "http://swisslakecapital.com/assets/download.jpeg",
          author: "Kirsty",
        },
        {
          quote: "A wonderful new experience",
          image: "http://swisslakecapital.com/assets/ava-e.png",
          author: "Padraig",
        },
        // More testimonials can be added here...
        {
          quote: "Fully meet expectations for a capsule hotel",
          image: "https://xx.bstatic.com/static/img/review/avatars/ava-a.png",
          author: "Angela",
        },
        {
          quote: "Good price",
          image: "https://xx.bstatic.com/static/img/review/avatars/ava-l.png",
          author: "Lorna",
        },
        {
          quote: "Nice stay in Zurich",
          image: "https://xx.bstatic.com/static/img/review/avatars/ava-l.png",
          author: "Leila",
        },
        {
          quote: "A wonderful new experience",
          image: "https://xx.bstatic.com/static/img/review/avatars/ava-l.png",
          author: "Padraig",
        },
        {
          quote: "Zurich with a budget: you can do it",
          image:
            "https://graph.facebook.com/v2.9/10206898736123536/picture?type=square&height=64&width=64",
          author: "Daniel",
        },
        {
          quote: "A wonderful new experience",
          image: "https://xx.bstatic.com/static/img/review/avatars/ava-l.png",
          author: "Padraig",
        },
        {
          quote: "I like it in general",
          image: "https://xx.bstatic.com/static/img/review/avatars/ava-j.png",
          author: "Jovanie",
        },
        {
          quote: "A Hostel with hospitality",
          image: "https://xx.bstatic.com/static/img/review/avatars/ava-r.png",
          author: "Renae",
        },
        {
          quote: "Very good",
          image: "https://xx.bstatic.com/static/img/review/avatars/ava-j.png",
          author: "John",
        },
        {
          quote: "Victoria",
          image: "https://xx.bstatic.com/static/img/review/avatars/ava-v.png",
          author: "Victoria",
        },
        {
          quote: "Good Afordable Place",
          image: "https://xx.bstatic.com/static/img/review/avatars/ava-d.png",
          author: "Dafsin",
        },
        {
          quote: "Good value, great location",
          image: "https://xx.bstatic.com/static/img/review/avatars/ava-s.png",
          author: "Suzanne",
        },
        {
          quote: "Superb",
          image:
            "https://xx.bstatic.com/xdata/images/xphoto/square64/42158920.jpg?k=f15a0dc7bf128ba57cbc659a454f76e0089cfb4e1c53a581930f160f6f97b53d&o=",
          author: "Vinnie",
        },
        {
          quote: "Good place for couple nights in the center of Zurich",
          image: "https://xx.bstatic.com/static/img/review/avatars/ava-d.png",
          author: "Daniel",
        },
        {
          quote:
            "Only recommend if you are extremely tight on budget. Not the ost comfortable and clean hostel",
          image: "https://xx.bstatic.com/static/img/review/avatars/ava-y.png",
          author: "Yana",
        },
        {
          quote: "Short and sweet",
          image: "https://xx.bstatic.com/static/img/review/avatars/ava-n.png",
          author: "Natalia",
        },
        {
          quote: "Great Hostel to know Zurich",
          image: "https://xx.bstatic.com/static/img/review/avatars/ava-j.png",
          author: "Joaquin",
        },
        {
          quote: "Great value for money. Loved it!",
          image: "https://xx.bstatic.com/static/img/review/avatars/ava-n.png",
          author: "Nada",
        },
        {
          quote: "A pleasant stay, would definitely come back!",
          image: "https://xx.bstatic.com/static/img/review/avatars/ava-a.png",
          author: "Alex",
        },
        {
          quote:
            "The staff was very friendly and accommodating. Great experience.",
          image: "https://xx.bstatic.com/static/img/review/avatars/ava-j.png",
          author: "Jordan",
        },
        {
          quote: "Excellent value for money, and the location is perfect.",
          image: "https://xx.bstatic.com/static/img/review/avatars/ava-t.png",
          author: "Taylor",
        },
        {
          quote: "Loved the interior design and cozy atmosphere.",
          image: "https://xx.bstatic.com/static/img/review/avatars/ava-r.png",
          author: "Riley",
        },
        {
          quote: "Perfect for a weekend stay. Clean and comfortable.",
          image: "https://xx.bstatic.com/static/img/review/avatars/ava-m.png",
          author: "Morgan",
        },
        {
          quote:
            "A wonderful experience overall, great location and facilities.",
          image: "https://xx.bstatic.com/static/img/review/avatars/ava-s.png",
          author: "Sam",
        },
        {
          quote: "The room was clean and had everything I needed.",
          image: "https://xx.bstatic.com/static/img/review/avatars/ava-c.png",
          author: "Casey",
        },
        {
          quote: "Nice atmosphere, comfortable rooms, and very affordable.",
          image: "https://xx.bstatic.com/static/img/review/avatars/ava-j.png",
          author: "Jesse",
        },
        {
          quote: "Great for travelers looking for an affordable option.",
          image: "https://xx.bstatic.com/static/img/review/avatars/ava-c.png",
          author: "Charlie",
        },
        {
          quote: "Very welcoming and clean. Will come back again.",
          image: "https://xx.bstatic.com/static/img/review/avatars/ava-a.png",
          author: "Avery",
        },
        {
          quote: "Fantastic service, staff was really kind and attentive.",
          image: "https://xx.bstatic.com/static/img/review/avatars/ava-a.png",
          author: "Alexis",
        },
        {
          quote: "A great place to stay on a budget, very satisfied.",
          image: "https://xx.bstatic.com/static/img/review/avatars/ava-p.png",
          author: "Peyton",
        },
        {
          quote: "Clean and tidy, perfect location for sightseeing.",
          image: "https://xx.bstatic.com/static/img/review/avatars/ava-b.png",
          author: "Blake",
        },
        {
          quote: "Simple, comfortable, and excellent value for money.",
          image: "https://xx.bstatic.com/static/img/review/avatars/ava-q.png",
          author: "Quinn",
        },
        {
          quote: "Amazing experience, very cozy atmosphere and kind staff.",
          image: "https://xx.bstatic.com/static/img/review/avatars/ava-s.png",
          author: "Skyler",
        },
        {
          quote: "Great location, nice rooms, and very friendly staff.",
          image: "https://xx.bstatic.com/static/img/review/avatars/ava-h.png",
          author: "Harper",
        },
        {
          quote: "Affordable and convenient, great for solo travelers.",
          image: "https://xx.bstatic.com/static/img/review/avatars/ava-f.png",
          author: "Finley",
        },
        {
          quote: "Everything was as described, clean and comfortable.",
          image: "https://xx.bstatic.com/static/img/review/avatars/ava-r.png",
          author: "Reese",
        },
        {
          quote: "The facilities were great, and the staff were very helpful.",
          image: "https://xx.bstatic.com/static/img/review/avatars/ava-k.png",
          author: "Kai",
        },
        {
          quote: "Had a great stay. Will definitely recommend to friends.",
          image: "https://xx.bstatic.com/static/img/review/avatars/ava-r.png",
          author: "River",
        },
        {
          quote: "Perfect for budget travel, cozy and convenient.",
          image: "https://xx.bstatic.com/static/img/review/avatars/ava-e.png",
          author: "Elliot",
        },
        {
          quote: "Very happy with my stay, great value for money.",
          image: "https://xx.bstatic.com/static/img/review/avatars/ava-r.png",
          author: "Rory",
        },
        {
          quote: "Friendly staff, clean rooms, and great atmosphere.",
          image: "https://xx.bstatic.com/static/img/review/avatars/ava-r.png",
          author: "Rowan",
        },
        {
          quote: "A wonderful experience, would stay here again.",
          image: "https://xx.bstatic.com/static/img/review/avatars/ava-e.png",
          author: "Emerson",
        },
        {
          quote: "Affordable, clean, and very convenient location.",
          image: "https://xx.bstatic.com/static/img/review/avatars/ava-h.png",
          author: "Hayden",
        },
        {
          quote: "The perfect place to stay when visiting the city.",
          image: "https://xx.bstatic.com/static/img/review/avatars/ava-d.png",
          author: "Dakota",
        },
        {
          quote: "Staff were really helpful, and the room was spotless.",
          image: "https://xx.bstatic.com/static/img/review/avatars/ava-r.png",
          author: "Remy",
        },
        {
          quote: "Everything was as expected. Great value for money.",
          image: "https://xx.bstatic.com/static/img/review/avatars/ava-k.png",
          author: "Kendall",
        },
        {
          quote: "Enjoyed my stay, great facilities and helpful staff.",
          image: "https://xx.bstatic.com/static/img/review/avatars/ava-a.png",
          author: "Aubrey",
        },
        {
          quote: "Perfect for a weekend visit, cozy and comfortable.",
          image: "https://xx.bstatic.com/static/img/review/avatars/ava-p.png",
          author: "Phoenix",
        },
        {
          quote: "Nice and clean, great location, and helpful staff.",
          image: "https://xx.bstatic.com/static/img/review/avatars/ava-j.png",
          author: "Jaden",
        },
        {
          quote: "The rooms were very comfortable, and the staff were kind.",
          image: "https://xx.bstatic.com/static/img/review/avatars/ava-h.png",
          author: "Hunter",
        },
        {
          quote: "Clean rooms, friendly staff, and very affordable.",
          image: "https://xx.bstatic.com/static/img/review/avatars/ava-r.png",
          author: "Reagan",
        },
        {
          quote: "Great experience, would definitely stay here again.",
          image: "https://xx.bstatic.com/static/img/review/avatars/ava-s.png",
          author: "Spencer",
        },
        {
          quote: "Amazing place to stay, very comfortable and clean.",
          image: "https://xx.bstatic.com/static/img/review/avatars/ava-p.png",
          author: "Presley",
        },
        {
          quote: "Good value for money, friendly staff, and clean rooms.",
          image: "https://xx.bstatic.com/static/img/review/avatars/ava-s.png",
          author: "Sage",
        },
        {
          quote: "A very nice experience, everything was perfect.",
          image: "https://xx.bstatic.com/static/img/review/avatars/ava-p.png",
          author: "Parker",
        },
        {
          quote: "Loved the vibe, comfortable rooms, and helpful staff.",
          image: "https://xx.bstatic.com/static/img/review/avatars/ava-p.png",
          author: "Payton",
        },
        {
          quote: "Great stay, everything was clean and comfortable.",
          image: "https://xx.bstatic.com/static/img/review/avatars/ava-a.png",
          author: "Arden",
        },
        {
          quote: "Comfortable beds, clean rooms, and a great location.",
          image: "https://xx.bstatic.com/static/img/review/avatars/ava-l.png",
          author: "Logan",
        },
        {
          quote: "Really enjoyed my stay, good facilities and location.",
          image: "https://xx.bstatic.com/static/img/review/avatars/ava-s.png",
          author: "Sawyer",
        },
        {
          quote: "A very pleasant experience, everything was perfect.",
          image: "https://xx.bstatic.com/static/img/review/avatars/ava-m.png",
          author: "Micah",
        },
        {
          quote: "Clean, cozy, and great for budget travelers.",
          image: "https://xx.bstatic.com/static/img/review/avatars/ava-j.png",
          author: "Justice",
        },
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
