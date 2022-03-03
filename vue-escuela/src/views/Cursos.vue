<style>
@import url("https://fonts.googleapis.com/css2?family=Leckerli+One&display=swap");
</style>
<template>
  <div>
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
    <v-layout justify-center align-center mt-5>
      <v-flex class="text-h6 pa-1" xs12>
        <p class="text-center">
          <v-btn icon> </v-btn>
          <!-- <input
            class="outlined"
            type="text"
            v-model="search"
            placeholder="Buscar cursos"
            dark
          /> -->
          <v-container style="width: 40vh">
            <v-text-field
              type="text"
              v-model="search"
              placeholder="Escribe el nombre del curso"
              label="Buscar cursos"
            >
              <v-icon slot="prepend" color="green">mdi-magnify</v-icon>
            </v-text-field>
          </v-container>
        </p>
      </v-flex>
    </v-layout>
    <!-- <v-container>
      <v-layout justify-center align-center mb-5>
        <v-flex class="text-h6" mb-5 mt-5>
          <input
            class="outlined pa-1"
            type="text"
            v-model="search"
            placeholder="Buscar cursos"
          />
          <v-btn icon>
            <v-icon>mdi-magnify</v-icon>
          </v-btn></v-flex
        >
      </v-layout>
    </v-container> -->
    <v-layout justify-center align-center wrap>
      <v-flex
        v-for="categoria in filteredCourses"
        mb-1
        :key="categoria.id"
        xs12
        sm8
        md8
        lg8
        pa-5
      >
        <v-card class="mx-auto" outlined>
          <v-list-item three-line>
            <v-list-item-content>
              <div class="text-overline mb-4">{{ categoria.nombre }}</div>
              <v-list-item-title class="text-h5 mb-1">
                {{ categoria.subtitulo }}
              </v-list-item-title>
              <v-list-item-subtitle>
                {{ categoria.descripcion }}
              </v-list-item-subtitle>
              <v-card-actions>
                <v-btn dark color="yapaycolor " rounded href="/contacto">
                  Inscribete
                </v-btn>

                <v-col cols="auto">
                  <v-dialog
                    transition="dialog-bottom-transition"
                    max-width="600"
                  >
                    <template v-slot:activator="{ on, attrs }">
                      <v-btn outlined rounded text v-bind="attrs" v-on="on"
                        >más información</v-btn
                      >
                    </template>
                    <template v-slot:default="dialog">
                      <v-card>
                        <v-toolbar color="primary" dark
                          >Opening from the bottom</v-toolbar
                        >
                        <v-card-text>
                          <div class="text-h6 pa-12">
                            {{ categoria.nombre }}
                          </div>
                        </v-card-text>
                        <v-card-actions class="justify-end">
                          <v-btn text @click="dialog.value = false"
                            >Close</v-btn
                          >
                        </v-card-actions>
                      </v-card>
                    </template>
                  </v-dialog>
                </v-col>
              </v-card-actions>
            </v-list-item-content>
            <v-img :src="categoria.url" max-width="30vw" height="200px"></v-img>
          </v-list-item>
        </v-card>

        <!-- <v-card class="mx-auto mt-5">
          <v-img :src="categoria.url" height="200px"></v-img>

          <v-card-title> {{ categoria.nombre }} </v-card-title>

          <v-card-subtitle> {{ categoria.subtitulo }}</v-card-subtitle>

          <v-card-actions> </v-card-actions>
        </v-card> -->
      </v-flex>
    </v-layout>
    <v-container style="height: 65vh"></v-container>
  </div>
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
        descripcion:
          "curso de community Manager curso de community Manager curso de community Manager​​ curso de community Manager​​ curso de community Manager curso de community Manager​​curso de community Manager curso de community Manager​​curso de community Manager curso de community Manager​​curso de community Manager curso de community Manager​​",
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
      {
        id: 8,
        nombre: "Curso Illustrato intermedio",
        subtitulo: "curso de illustrato intermedio",
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
      {
        id: 8,
        nombre: "Curso Illustrato intermedio",
        subtitulo: "curso de illustrato intermedio",
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