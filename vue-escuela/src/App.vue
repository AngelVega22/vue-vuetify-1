
<template>
  <v-app>
    <Navbar />
    <MobileNav />
    <v-main>
      <router-view />
    </v-main>
    <Footer />
  </v-app>
</template>



<script>
import Navbar from "./components/Navbar.vue";
import MobileNav from "./components/MobileNav.vue";
import Footer from "./components/Footer.vue";
export default {
  name: "App",
  components: {
    Navbar,
    MobileNav,
    Footer,
  },
};
</script>
