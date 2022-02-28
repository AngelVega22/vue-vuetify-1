<template>
  <v-app>
    <v-toolbar elevation="4" prominent>
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
            <v-btn text large href="/"
              ><p class="white--text">Escuela</p>
            </v-btn>
            <v-btn text large href="/cursos">
              <p class="white--text">Cursos</p>
            </v-btn>
            <v-btn text large> <p class="white--text">Contacto</p> </v-btn>
              </v-btn>
            <v-btn text large href="https://yapaydigital.pe/"> <p class="white--text">Agencia</p> </v-btn>
          </v-container>
        </v-tabs>
      </template>
    </v-toolbar>

    <v-main>
      <router-view />
    </v-main>
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
