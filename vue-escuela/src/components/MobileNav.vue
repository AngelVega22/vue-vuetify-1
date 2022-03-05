<template>
  <section>
    <v-toolbar class="hidden-md-and-up yapaycolor" app>
      <div>
        <v-container>
          <a href="/">
            <v-img src="/img/logo-sm.svg" max-width="45px"></v-img>
          </a>
        </v-container>
      </div>
      <v-app-bar-nav-icon @click.stop="drawer = !drawer"></v-app-bar-nav-icon>
    </v-toolbar>
    <v-navigation-drawer v-model="drawer" absolute temporary>
      <v-list-item>
        <a href="/"><v-img src="/img/escuela.png" max-width="220px"></v-img></a>

        <v-list-item-content>
          <!-- <v-list-item-title>John Leider</v-list-item-title> -->
        </v-list-item-content>
      </v-list-item>

      <!-- <v-card class="mx-auto"> -->
      <v-list class="grow">
        <v-list-item>
          <v-list-item-content>
            <v-btn text>
              <router-link class="black--text text-decoration-none pa-5" to="/">
                Escuela</router-link
              ></v-btn
            >
            <v-btn text>
              <router-link
                class="black--text text-decoration-none pa-5"
                to="/cursos"
                >Cursos</router-link
              ></v-btn
            >
            <v-btn text>
              <router-link
                class="black--text text-decoration-none pa-5"
                to="/contacto"
                >Inscríbete</router-link
              ></v-btn
            >
            <v-btn text>
              <a
                target="_blank"
                class="black--text text-decoration-none pa-5"
                href="https://yapaydigital.pe/"
                >Agencia</a
              ></v-btn
            >
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
  </section>
</template>

<script>
export default {
  data: () => ({
    drawer: false,
    group: null,
  }),

  watch: {
    group() {
      this.drawer = false;
    },
  },
};
</script>
