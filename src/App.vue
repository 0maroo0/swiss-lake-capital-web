<template>
  <NavBar />
  <Home />
  <About />
  <ServicesView />
  <Contactus />
  <FooterView />
  <FloatingIcon />
</template>

<script>
// @ is an alias to /src
import NavBar from "@/components/nav.vue";
import FloatingIcon from "@/components/floating_whatsapp.vue";
import Home from "@/views/HomeView.vue";
import About from "@/views/AboutView.vue";
import Contactus from "@/views/contact_us.vue";
import ServicesView from "@/views/ServicesView.vue";
import FooterView from "@/views/footerView.vue";

export default {
  name: "HomeView",
  components: {
    NavBar,
    Home,
    About,
    ServicesView,
    Contactus,
    FooterView,
    FloatingIcon,
  },
};
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

nav {
  padding: 30px;
  margin-right: 5px;

  a {
    font-weight: bold;
    color: #2c3e50;

    &.router-link-exact-active {
      margin-right: 5px;

      color: #42b983;
    }
  }
}
</style>
