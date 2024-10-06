<template>
  <section id="contact" class="contact">
    <h2 class="contact-us">Contact Us</h2>
    <div class="contact-us-container">
      <!-- Map & Contact Form in Row -->
      <div class="row-container">
        <div class="map-container">
          <iframe
            src="https://www.mapillary.com/embed?map_style=Mapillary%20light&image_key=2561886500771534&x=0.5&y=0.5&style=photo"
            frameborder="0"
          ></iframe>
        </div>

        <!-- Contact Form -->
        <form @submit.prevent="handleSubmit">
          <h1 class="title text-center mb-4">Talk to Us</h1>

          <!-- Name -->
          <div class="form-group position-relative">
            <label for="formName" class="d-block">
              <i class="icon" data-feather="user"></i>
            </label>
            <input
              type="text"
              id="formName"
              class="form-control form-control-lg thick"
              placeholder="Name"
              v-model="name"
              required
            />
          </div>

          <!-- E-mail -->
          <div class="form-group position-relative">
            <label for="formEmail" class="d-block">
              <i class="icon" data-feather="mail"></i>
            </label>
            <input
              type="email"
              id="formEmail"
              class="form-control form-control-lg thick"
              placeholder="E-mail"
              v-model="email"
              required
            />
          </div>

          <!-- Message -->
          <div class="form-group message">
            <textarea
              id="formMessage"
              class="form-control form-control-lg"
              rows="7"
              placeholder="Your Message"
              v-model="message"
              required
            ></textarea>
          </div>

          <!-- Submit button -->
          <div class="text-center">
            <button type="submit" class="btn btn-primary">Send message</button>
          </div>
        </form>
      </div>

      <!-- Map Image Below Row -->
      <div class="map-image-container">
        <a
          href="https://www.mapillary.com/app/?pKey=2561886500771534&focus=photo"
        >
          <img
            src="../assets/Greenmarmot_map.png"
            alt="Map Thumbnail"
            class="map-image"
          />
        </a>
      </div>
    </div>
  </section>
</template>

<script>
import axios from "axios";
export default {
  name: "ContactUs",
  data() {
    return {
      name: "",
      email: "",
      message: "",
    };
  },
  methods: {
    async handleSubmit() {
      try {
        console.log("Form submitted:", {
          name: this.name,
          email: this.email,
          message: this.message,
        });

        // Prepare form data
        const formData = new FormData();
        formData.append("name", this.name);
        formData.append("email", this.email);
        formData.append("message", this.message);

        // Send POST request
        const response = await axios.post(
          "https://morabrand.net/bemocode/public/api/sendmail",
          formData
        );
        console.log("Response:", response.data);

        // Handle success (e.g., show a success message)
      } catch (error) {
        console.error("Error sending data:", error);
        // Handle error (e.g., show an error message)
      }
    },
  },
};
</script>
<style scoped lang="scss">
.contact-us {
  font-size: 2em;
  color: #2c3e50;
  text-align: center;
  padding: 20px;
  margin: 20px 0;
  position: relative;
}

.contact-us::after {
  content: "";
  display: block;
  width: 50px;
  height: 4px;
  background: #3498db;
  margin: 10px auto 0;
}

.contact-us-container {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  margin: 20px;
  border-radius: 8px;
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
  height: auto;
}

.row-container {
  display: flex;
  flex-direction: row;
  width: 100%;
  margin-bottom: 20px;
}

.map-container,
form {
  flex: 1;
  border: 2px solid #007bff;
  border-radius: 8px;
  overflow: hidden;
  margin-right: 20px;
}

iframe {
  width: 100%;
  height: 100%;
  border: none;
}

form {
  padding: 20px;
  background-color: #f8f9fa;
  border-radius: 8px;
  display: flex;
  flex-direction: column;
  justify-content: center;
}

.title {
  font-family: "Pacifico", cursive;
  color: #212529;
  font-size: 2.5rem;
  margin-bottom: 20px;
}

.form-group {
  margin-bottom: 15px;
}

label {
  margin-bottom: 5px;
  font-weight: bold;
  color: #ffffff;
}

input,
textarea {
  width: 100%;
  padding: 10px;
  border: 1px solid #ccc;
  border-radius: 5px;
  transition: border-color 0.3s;
  font-family: "Quicksand", sans-serif;
  color: #212529;
  font-size: 1.1rem;
}

input:focus,
textarea:focus {
  border-color: wheat;
}

textarea {
  resize: none;
}

.btn.btn-primary {
  font-family: "Quicksand", sans-serif;
  font-weight: bold;
  padding: 10px 20px;
  border: none;
  border-radius: 5px;
  color: white;
  background-color: #2947a9;
  transition: all 0.3s ease-in-out;
  cursor: pointer;
}

.btn.btn-primary:hover {
  color: wheat;
  background-color: #0f39c1;
}

.map-image-container {
  margin-top: 20px;
  text-align: center;
}

.map-image {
  width: 100%;
  height: auto;
  object-fit: cover;
  margin-top: 10px;
  border-radius: 5px;
}

/* Mobile Styles */
@media (max-width: 768px) {
  .row-container {
    flex-direction: column;
  }

  .map-container,
  form {
    margin-right: 0;
    margin-bottom: 20px;
  }

  .title {
    font-size: 2rem;
  }

  input,
  textarea {
    font-size: 1rem;
  }

  .btn.btn-primary {
    padding: 10px;
    font-size: 1rem;
  }
}
</style>
