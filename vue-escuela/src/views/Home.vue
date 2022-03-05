<template>
  <section>
    <!--<v-layout justify-center
      align-center
      mt-5
      class="secondary"
      style="height: 50vh"
    >
      <v-flex class=" pa-5" xs3>
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
