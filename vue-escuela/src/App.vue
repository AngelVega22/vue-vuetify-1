<style>
.container {
  width: 100%;
  padding: 6px !important;
}
</style>
<template>
  <v-app>
    <v-app-bar class="yapaycolor hidden-sm-and-down" prominent>
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
        <v-tabs class="yapaycolor hidden-sm-and-down">
          <v-container>
            <router-link
              class="hidden-sm-and-down white--text text-decoration-none pa-5"
              to="/"
              >Escuela</router-link
            >

            <router-link
              class="hidden-sm-and-down white--text text-decoration-none pa-5"
              to="/cursos"
              >cursos</router-link
            >

            <router-link
              class="hidden-sm-and-down white--text text-decoration-none pa-5"
              to="/contacto"
              >Contacto</router-link
            >
          </v-container>
        </v-tabs>
      </template>
    </v-app-bar>
    <!--====================-->
    <v-toolbar class="hidden-sm-and-up yapaycolor" app>
      <v-app-bar-nav-icon @click.stop="drawer = !drawer"></v-app-bar-nav-icon>
    </v-toolbar>
    <v-navigation-drawer v-model="drawer" absolute temporary>
      <v-list-item>
        <v-img src="/img/escuela.png" max-width="220px"></v-img>

        <v-list-item-content>
          <!-- <v-list-item-title>John Leider</v-list-item-title> -->
        </v-list-item-content>
      </v-list-item>

      <v-card class="mx-auto">
        <v-list class="grow">
          <v-list-item>
            <v-list-item-action> </v-list-item-action>

            <v-list-item-content>
              <router-link class="black--text text-decoration-none pa-5" to="/">
                Escuela</router-link
              >
              <router-link
                class="black--text text-decoration-none pa-5"
                to="/cursos"
                >Cursos</router-link
              >
              <router-link
                class="black--text text-decoration-none pa-5"
                to="/contacto"
                >Contacto</router-link
              >
            </v-list-item-content>
          </v-list-item>
        </v-list>
      </v-card>
    </v-navigation-drawer>
    <!--=====================-->

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
