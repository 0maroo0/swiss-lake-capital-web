<template>
  <section id="contact" class="contact">
    <h2 class="contact-us">Contact Us</h2>
    <div class="contact-us-container">
      <div class="map-container">
        <iframe
          src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d2858.3326083070574!2d6.151577583058235!3d46.211103552835446!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x478c65240874caa3%3A0x989130d4d80a02f0!2zUnVlIGRlIGxhIE5hdmlnYXRpb24gMywgMTIwMSBHZW7DqHZlLCDYs9mI2YrYs9ix2Kc!5e0!3m2!1sar!2seg!4v1727623046031!5m2!1sar!2seg"
          width="100%"
          height="100%"
          style="border: 0"
          allowfullscreen=""
          loading="lazy"
          referrerpolicy="no-referrer-when-downgrade"
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

        <!-- Submit btn -->
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
      // You can add form handling logic here (like sending data to a server)
    },
  },
};
</script>

<style scoped lang="scss">
.contact-us {
  font-size: 2em; /* Large font size */
  color: #2c3e50; /* Dark color */
  text-align: center; /* Centered text */
  padding: 20px; /* Padding around the text */
  margin: 20px 0; /* Margin above and below */
  position: relative; /* Position for pseudo-element */
}

.contact-us::after {
  content: ""; /* Create a decorative line */
  display: block;
  width: 50px; /* Width of the line */
  height: 4px; /* Height of the line */
  background: #3498db; /* Color of the line */
  margin: 10px auto 0; /* Center the line below the text */
}

.contact-us-container {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  margin: 20px;
  border-radius: 8px;
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
  height: 600px; /* Set a fixed height for the layout */
}

.map-container {
  flex: 1;
  border: 2px solid #007bff; /* Blue border for the map */
  border-radius: 8px 0 0 8px; /* Rounded corners */
  overflow: hidden;
}

form {
  flex: 1;
  padding: 20px;
  background-color: #f8f9fa; /* Light background color */
  border: 2px solid; /* Blue border for the form */
  border-radius: 0 8px 8px 0; /* Rounded corners */
  display: flex;
  flex-direction: column;
  justify-content: center;
}

.title {
  font-family: "Pacifico", cursive;
  color: #212529;
  font-size: 2.5rem;
  margin-bottom: 20px; /* Margin below title */
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
  border-color: wheat; /* Blue border on focus */
}

textarea {
  resize: none; /* Disable resizing for textarea */
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
    flex-direction: column; /* Stack map and form on mobile */
    height: auto; /* Remove fixed height for mobile */
    width: 95%;
  }

  .map-container {
    border-radius: 8px 8px 0 0; /* Rounded corners on top */
    height: 300px; /* Set a smaller height for the map */
  }

  form {
    border-radius: 0 0 8px 8px; /* Rounded corners on bottom */
    padding: 35px; /* Reduce padding on mobile */
  }

  .title {
    font-size: 2rem; /* Smaller title on mobile */
  }

  input,
  textarea {
    font-size: 1rem; /* Smaller input and textarea font size */
  }

  .btn.btn-primary {
    padding: 10px; /* Smaller button padding */
    font-size: 1rem; /* Smaller button font size */
  }
}
</style>
