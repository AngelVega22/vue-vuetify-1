<style>
@import url("https://fonts.googleapis.com/css2?family=Leckerli+One&display=swap");
.outlined {
  border: thin solid #00849d;
  border-radius: 2%;
}
</style>
<template>
  <v-container>
    <v-layout justify-center>
      <v-flex class="display-1 pa-5 mb-5 mt-5" yapaycolor--text xs12>
        <h1
          class="text-center font-weight-thin"
          style="font-family: 'Leckerli One', cursive"
        >
          Cursos
        </h1></v-flex
      ></v-layout
    >

    <v-layout justify-center align-center mb-5>
      <v-flex class="h4" mb-5 mt-5>
        <input
          class="outlined pa-2"
          type="text"
          v-model="search"
          placeholder="Buscar cursos"
        />
        <v-btn icon>
          <v-icon>mdi-magnify</v-icon>
        </v-btn></v-flex
      >
    </v-layout>

    <v-layout justify-center align-center wrap>
      <v-flex
        v-for="categoria in filteredCourses"
        mb-5
        :key="categoria.id"
        xs12
        sm6
        md4
        lg3
      >
        <v-card class="mx-auto mt-5" max-width="360">
          <v-img :src="categoria.url" height="200px"></v-img>

          <v-card-title> {{ categoria.nombre }} </v-card-title>

          <v-card-subtitle> {{ categoria.subtitulo }}</v-card-subtitle>

          <v-card-actions> </v-card-actions>
        </v-card>
      </v-flex>
    </v-layout>
    <v-container style="height: 65vh"></v-container>
  </v-container>
</template>
<script>
export default {
  name: "Cursos",
  data: () => ({
    show: false,
    categorias: [
      {
        id: 1,
        nombre: "Community Manager",
        subtitulo: "curso de community Manager",
        descripcion: "​​",
        url: " /img/mktdig.jpg",
      },
      {
        id: 2,
        nombre: "Branding",
        subtitulo: "curso de branding",
        descripcion: "",
        url: "/img/dweb.jpg",
      },
      {
        id: 3,
        nombre: "Facebook y whatsApp",
        subtitulo: "curso de facebook y whatsapp",
        descripcion: "",
        url: "/img/disgr.jpg",
      },
      {
        id: 4,
        nombre: "Taller instagram",
        subtitulo: "taller de instagram",
        descripcion: "",
        url: "/img/disgr.jpg",
      },
      {
        id: 5,
        nombre: "Curso personal branding",
        subtitulo: "curso de personal branding",
        descripcion: "",
        url: "/img/disgr.jpg",
      },
      {
        id: 6,
        nombre: "Curso Photoshop intermedio",
        subtitulo: "curso de photoshop intermedio",
        descripcion: "",
        url: "/img/disgr.jpg",
      },
      {
        id: 7,
        nombre: "Curso Photoshop avanzado",
        subtitulo: "curso de photoshop avanzado",
        descripcion: "",
        url: "/img/disgr.jpg",
      },
      {
        id: 8,
        nombre: "Curso Illustrato intermedio",
        subtitulo: "curso de illustrato intermedio",
        descripcion: "",
        url: "/img/disgr.jpg",
      },
    ],
    search: "",
  }),
  computed: {
    filteredCourses: function () {
      return this.categorias.filter((categoria) => {
        return categoria.subtitulo.match(this.search);
      });
    },
  },
};
</script>