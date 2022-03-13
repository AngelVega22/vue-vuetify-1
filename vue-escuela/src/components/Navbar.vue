<style>
.container {
  width: 100%;
  padding: 6px !important;
}
</style>
<template>
  <v-app-bar class="hidden-sm-and-down" prominent >
    <div>
      <v-container>
        <a href="/">
          <v-img src="/img/escuela.png" max-width="220px" class="ml-5"></v-img>
        </a>
      </v-container>
    </div>

    <template v-slot:extension>
      <v-tabs class="yapaycolor">
        <v-container>
          <v-btn text>
            <router-link class="white--text text-decoration-none pa-5" to="/"
              >Escuela</router-link
            ></v-btn
          >
          <v-btn text>
            <router-link
              class="white--text text-decoration-none pa-5"
              to="/cursos"
              >cursos</router-link
            ></v-btn
          >
                  <v-btn text>
            <router-link
              class="white--text text-decoration-none pa-5"
              to="/docentes"
              >docentes</router-link
            ></v-btn
          >
          <v-btn text>
            <router-link
              class="white--text text-decoration-none pa-5"
              to="/contacto"
              >Inscríbete</router-link
            ></v-btn
          >
          <v-btn text>
            <a
              target="_blank"
              class="white--text text-decoration-none pa-5"
              href="https://yapaydigital.pe/"
              >Agencia</a
            ></v-btn
          >
        </v-container>
      </v-tabs>
    </template>
  </v-app-bar>
</template>
<script>
export default {
  name: "Navbar",

  components: {}
};
</script>