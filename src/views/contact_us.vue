<template>
  <section id="contact" class="contact">
    <h2 class="contact-us">Contact Us</h2>
    <div class="contact-us-container">
      <div class="map-container">
        <iframe
          width="640"
          height="180"
          src="https://www.mapillary.com/embed?map_style=Mapillary%20light&image_key=2561886500771534&x=0.5&y=0.5&style=photo"
          frameborder="0"
        ></iframe>
        <div class="map-overlay">
          <div class="map-label">Green marmot</div>
        </div>
        <a
          href="https://www.mapillary.com/app/?pKey=2561886500771534&focus=photo"
          ><img src="../assets/Greenmarmot_map.png"
        /></a>
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
  </section>
</template>

<script>
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
    handleSubmit() {
      console.log("Form submitted:", {
        name: this.name,
        email: this.email,
        message: this.message,
      });
      // Add form handling logic (e.g., sending data to a server)
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
  flex-direction: row;
  justify-content: space-between;
  margin: 20px;
  border-radius: 8px;
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
  height: 600px;
}

.map-container {
  position: relative;
  flex: 1;
  border: 2px solid #007bff;
  border-radius: 8px 0 0 8px;
  overflow: hidden;
}

.map-overlay {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  pointer-events: none;
}

.map-label {
  color: green;
  padding: 10px;
  font-size: 14px;
  border-radius: 5px;
  font-weight: bold;
  text-align: center; /* Use center instead of 900 */
}

form {
  flex: 1;
  padding: 20px;
  background-color: #f8f9fa;
  border: 2px solid;
  border-radius: 0 8px 8px 0;
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

/* Mobile Styles */
@media (max-width: 768px) {
  .contact-us-container {
    flex-direction: column;
    height: auto;
    width: 95%;
  }

  .map-container {
    border-radius: 8px 8px 0 0;
    height: 300px;
  }

  form {
    border-radius: 0 0 8px 8px;
    padding: 35px;
  }

  .title {
    font-size: 2rem;
  }

  input,
  textarea {
    font-size: 1rem;
  }

  .btn.btn-primary {
    // eslint-disable-next-line prettier/prettier
    padding: 10px;
    font-size: 1rem;
  }
}
</style>
