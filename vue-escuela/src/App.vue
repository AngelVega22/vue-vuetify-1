<style>
.container {
  width: 100%;
  padding: 6px !important;
}
</style>
<template>
  <v-app>
    <v-app-bar prominent>
      <div>
        <v-container>
          <a href="/">
            <v-img
              src="/img/escuela.png"
              max-width="220px"
              class="ml-5"
            ></v-img>
          </a>
        </v-container>
      </div>

      <template v-slot:extension>
        <v-tabs class="yapaycolor">
          <v-container>
            <!-- <v-btn text large href="/"
              ><p class="white--text">Escuela</p>
            </v-btn> -->
            <router-link class="white--text text-decoration-none pa-5" to="/"
              >Escuela</router-link
            >

            <router-link
              class="white--text text-decoration-none pa-5"
              to="/cursos"
              >cursos</router-link
            >
            <!-- <v-btn text large href="/cursos">
              <p class="white--text">Cursos</p>
            </v-btn> -->
            <router-link
              class="white--text text-decoration-none pa-5"
              to="/contacto"
              >Contacto</router-link
            >

            <!-- <v-btn text large href="/contacto">
              <p class="white--text">Contacto</p>
            </v-btn> -->
            <!-- <v-btn text large href="https://yapaydigital.pe/">
              <p class="white--text">Agencia</p>
            </v-btn> -->
          </v-container>
        </v-tabs>
      </template>
    </v-app-bar>

    <v-main>
      <router-view />
    </v-main>

    <template>
      <v-footer dark padless>
        <v-card class="flex" flat tile>
          <v-card-title class="yapaycolor">
            <strong class="subheading">¡Aprende con nosotros!</strong>

            <v-spacer></v-spacer>

            <v-btn v-for="icon in icons" :key="icon" class="mx-4" dark icon>
              <v-icon size="24px">
                {{ icon }}
              </v-icon>
            </v-btn>
          </v-card-title>

          <v-card-text class="py-2 white--text text-center">
            {{ new Date().getFullYear() }} — <strong>Angel Vega</strong>
          </v-card-text>
        </v-card>
      </v-footer>
    </template>
  </v-app>
</template>



<script>
export default {
  name: "App",

  data: () => ({
    //
  }),
};
</script>
