<template>
  <v-carousel cycle height="500" hide-delimiter-background show-arrows-on-hover>
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
          src: "https://images.pexels.com/photos/3769021/pexels-photo-3769021.jpeg?auto=compress&cs=tinysrgb&dpr=2&h=650&w=940",
        },
        {
          src: "https://images.pexels.com/photos/5940838/pexels-photo-5940838.jpeg?auto=compress&cs=tinysrgb&dpr=2&h=650&w=940",
        },
        {
          src: "https://images.pexels.com/photos/1438072/pexels-photo-1438072.jpeg?auto=compress&cs=tinysrgb&dpr=2&h=650&w=940",
        },
        {
          src: "https://images.pexels.com/photos/5198252/pexels-photo-5198252.jpeg?auto=compress&cs=tinysrgb&dpr=2&h=650&w=940",
        },
      ],
    };
  },
};
</script>