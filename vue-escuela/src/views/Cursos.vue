<style>
@import url("https://fonts.googleapis.com/css2?family=Leckerli+One&display=swap");
</style>
<template>
  <div>
    <v-layout justify-center>
      <v-flex class="display-1 pa-2 mt-5" yapaycolor--text xs12>
        <h1
          class="text-center font-weight-thin"
          style="font-family: 'Leckerli One', cursive"
        >
          Cursos
        </h1></v-flex
      ></v-layout
    >
    <v-layout justify-center align-center>
      <v-flex class="text-h6 pa-1" xs12 sm6 md6 lg4>
        <p class="text-center">
          <v-btn icon> </v-btn>
          <v-container>
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
        sm10
        md10
        lg8
        pa-1
      >
        <v-card class="mx-auto" outlined>
          <v-img
            class="hidden-md-and-up"
            :src="categoria.url"
            max-width="100vw"
            max-height="35vh"
          ></v-img>
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
                <v-col cols="auto">
                  <v-dialog fullscreen transition="dialog-bottom-transition">
                    <template v-slot:activator="{ on, attrs }">
                      <v-btn
                        class="mb-2"
                        outlined
                        rounded
                        text
                        v-bind="attrs"
                        v-on="on"
                        >más información</v-btn
                      >
                      <v-btn
                        dark
                        color="yapaycolor mb-2 "
                        rounded
                        href="/contacto"
                      >
                        Inscríbete
                      </v-btn>
                    </template>
                    <template v-slot:default="dialog">
                      <Navbar />
                      <MobileNav />
                      <v-card>
                        <v-toolbar color="grey darken-2" dark>
                          <v-btn
                            class="pa-2"
                            outlined
                            rounded
                            @click="dialog.value = false"
                          >
                            <v-icon> mdi-arrow-left </v-icon>Regresar</v-btn
                          ></v-toolbar
                        >
                        <v-card-text>
                          <div class="text-h3 pa-5"></div>
                          <v-layout wrap>
                            <v-flex xs12 lg6>
                              <v-img :src="categoria.url"></v-img>
                            </v-flex>
                            <v-flex xs12 lg6>
                              <div class="text-h4 px-5">
                                {{ categoria.nombre }}
                              </div>
                              <v-container pa-5>
                                <div>
                                  {{ categoria.descripcion }}
                                </div>
                              </v-container>
                              <Form />
                            </v-flex>
                          </v-layout>
                          <!-- <div class="text-h6 pa-5">
                            {{ categoria.descripcion }}
                          </div> -->
                        </v-card-text>

                        <v-card-actions class="justify-center">
                          <v-btn
                            dark
                            color="yapaycolor  "
                            rounded
                            href="/contacto"
                          >
                            Inscríbete
                          </v-btn>
                          <v-btn outlined rounded @click="dialog.value = false"
                            >Más cursos</v-btn
                          >
                        </v-card-actions>
                      </v-card>
                      <Footer />
                    </template>
                  </v-dialog>
                </v-col>
              </v-card-actions>
            </v-list-item-content>
            <v-img
              class="hidden-sm-and-down"
              :src="categoria.url"
              :lazy-src="categoria.url"
              max-width="30vw"
              max-height="25vh"
              aspect-ratio="1"
            >
              <template v-slot:placeholder>
                <v-skeleton-loader
                  class="mx-auto"
                  type="card"
                ></v-skeleton-loader>
              </template>
            </v-img>
          </v-list-item>
        </v-card>

        <!-- <v-card class="mx-auto mt-5">
          <v-img :src="categoria.url" height="200px"></v-img>

          <v-card-title> {{ categoria.nombre }} </v-card-title>

          <v-card-subtitle> {{ categoria.subtitulo }}</v-card-subtitle>

          <v-card-actions> </v-card-actions>
        </v-card> -->

        <!---->
      </v-flex>
    </v-layout>

    <v-container style="height: 65vh">
      <!-- <v-layout justify-center align-center wrap>
        <v-flex
          v-for="categoria in filteredCourses"
          mb-1
          :key="categoria.id"
          xs12
          sm3
          md3
          lg3
          pa-1
        >
          <v-card class="mx-auto mt-5">
            <v-img :src="categoria.url" height="200px"></v-img>

            <v-card-title> {{ categoria.nombre }} </v-card-title>

            <v-card-subtitle> {{ categoria.subtitulo }}</v-card-subtitle>

            <v-card-actions> </v-card-actions>
          </v-card>
        </v-flex>
      </v-layout> -->
    </v-container>
  </div>
</template>
<script>
import Navbar from "../components/Navbar.vue";
import MobileNav from "../components/MobileNav.vue";
import Footer from "../components/Footer.vue";
import Form from "../components/Form.vue";
export default {
  name: "Cursos",

  data: () => ({
    show: false,
    categorias: [
      {
        id: 1,
        nombre: "Facebook y whatsApp",
        subtitulo: "curso de facebook y whatsapp",
        descripcion: "",
        url: "img/cursos/CURSO-FACEBOOK-Y-WHATSAPP.jpg",
      },
      {
        id: 2,
        nombre: "Taller instagram",
        subtitulo: "taller de instagram",
        descripcion: "",
        url: "img/cursos/TALLER-INSTAGRAM.jpg",
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
  components: {
    Form,
    Navbar,
    MobileNav,
    Footer,
  },
};
</script>