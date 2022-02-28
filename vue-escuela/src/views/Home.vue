<template>
  <section>
    <!-- <v-layout wrap>
      <v-flex class="primary" xs12 md6 lg12>
        <h1>lorem</h1>
      </v-flex>
      <v-flex class="info" xs6 md6 lg6>
        <h1>lorem</h1>
      </v-flex>
    </v-layout>
    <v-layout
      justify-center
      align-center
      mt-5
      class="secondary"
      style="height: 50vh"
    >
      <v-flex class="pink lighten-1 white--text display-2 pa-5" xs3>
        <h1 class="text-center">lorem</h1></v-flex
      >
    </v-layout> -->
    <Carousel />

    <Cards />
  </section>
</template>

<script>
import Carousel from "../components/Carousel";
import Cards from "../components/Cards";
export default {
  name: "Home",

  components: {
    Carousel,
    Cards,
  },
};
</script>
