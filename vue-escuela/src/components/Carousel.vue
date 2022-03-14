<template>
  <v-carousel cycle height="550" hide-delimiter-background show-arrows-on-hover>
    <v-carousel-item
      v-for="(item, i) in items"
      :key="i"
      :src="item.src"
    ></v-carousel-item>
  </v-carousel>
</template>

<script>
export default {
  name: "Carousel",
  data() {
    return {
      items: [
        {
          src: "img/cursos/CURSO-FACEBOOK-Y-WHATSAPP.jpg"
        },
        {
          src: "img/cursos/TALLER-INSTAGRAM.jpg"
        },
        {
          src: "img/cursos/CURSO-COMMUNITY-MANAGER.jpg"
        }
      ]
    };
  }
};
</script>