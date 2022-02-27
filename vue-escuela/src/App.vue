<template>
  <v-app>
    <v-app-bar app dense elevation="1" rounded flat>
      <v-container>
        <v-btn text> Escuela </v-btn>
        <v-btn text> Cursos </v-btn>
        <v-btn text> Promociones </v-btn>
      </v-container>
    </v-app-bar>
    <Carousel />
    <Cards />
    <v-main>
      <router-view />
    </v-main>
  </v-app>
</template>

<script>
import Carousel from "./components/Carousel";
import Cards from "./components/Cards";
export default {
  name: "App",

  components: {
    Carousel,
    Cards,
  },

  data: () => ({
    //
  }),
};
</script>
