<style>
@import url("https://fonts.googleapis.com/css2?family=Leckerli+One&display=swap");
</style>

<template>
  <v-container>
    <v-layout justify-center wrap>
      <v-flex class="display-1 pa-5 mb-5 mt-5" yapaycolor--text xs12>
        <h1
          class="text-center font-weight-thin"
          style="font-family: 'Leckerli One', cursive"
        >
          Categorias
        </h1></v-flex
      ></v-layout
    >
    <v-spacer></v-spacer>

    <v-layout justify-center align-center wrap>
      <v-flex
        v-for="categoria in categorias"
        xs12
        sm6
        md4
        lg3
        pa-5
        :key="categoria.id"
      >
        <v-hover v-slot="{ hover }" open-delay="200">
          <v-card
            class="mx-auto mt-5"
            max-width="360"
            :elevation="hover ? 16 : 2"
            :class="{ 'on-hover': hover }"
          >
            <v-img
              :src="categoria.url"
              height="200px"
              aspect-ratio="1"
              class="grey lighten-2"
            >
              <template v-slot:placeholder>
                <v-row class="fill-height ma-0" align="center" justify="center">
                  <v-progress-circular
                    indeterminate
                    color="grey lighten-5"
                  ></v-progress-circular>
                </v-row>
              </template>
            </v-img>

            <v-card-title> {{ categoria.nombre }} </v-card-title>

            <v-card-subtitle> {{ categoria.subtitulo }}</v-card-subtitle>

            <v-card-actions>
              <div class="my-2 ml-2">
                <v-btn x-small color="yapaycolor" href="/cursos" dark>
                  ver más
                </v-btn>
              </div>
            </v-card-actions>
          </v-card>
        </v-hover>
      </v-flex>
    </v-layout>
    <v-container style="height: 10vh"> </v-container>
  </v-container>
</template>

<script>
export default {
  name: "Cards",
  data: () => ({
    show: false,
    categorias: [
      {
        id: 1,
        nombre: "Marketing Digital",
        subtitulo: "Cursos de marketing digital",
        descripcion:
          "El mercadeo digital es el componente de la mercadotecnia que utiliza internet y tecnologías digitales en línea, como computadoras de escritorio, teléfonos móviles y otras plataformas y medios digitales para promover productos y servicios.​​",
        url: " /img/mktdig.jpg",
      },
      {
        id: 2,
        nombre: "Desarrollo Web",
        subtitulo: "Cursos de desarrollo web",
        descripcion:
          "Desarrollo web es un término que define la creación de sitios web para Internet o una intranet.​​",
        url: "/img/dweb.jpg",
      },
      {
        id: 3,
        nombre: "Diseño gráfico",
        subtitulo: "Cursos de diseño gráfico",
        descripcion:
          "El diseño gráfico es la profesión y disciplina académica cuya actividad consiste en proyectar comunicaciones visuales destinadas a transmitir mensajes específicos a grupos sociales con objetivos determinados.",
        url: "/img/disgr.jpg",
      },
      {
        id: 4,
        nombre: "Audiovisual",
        subtitulo: "Cursos de audivisual",
        descripcion:
          "El concepto audiovisual significa la integración e interrelación plena entre lo auditivo y lo visual para producir una nueva realidad o lenguaje. La percepción es simultánea. Se crean así nuevas realidades sentidos|sensoriales mediante mecanismos como la armonía, complementaria, refuerzo y contraste.",
        url: "/img/AUDIOVISUAL.jpg",
      },
      {
        id: 5,
        nombre: "Coaching y aprendizaje",
        subtitulo: "Cursos de Coaching y aprendizaje",
        descripcion:
          "El concepto audiovisual significa la integración e interrelación plena entre lo auditivo y lo visual para producir una nueva realidad o lenguaje. La percepción es simultánea. Se crean así nuevas realidades sentidos|sensoriales mediante mecanismos como la armonía, complementaria, refuerzo y contraste.",
        url: "/img/coaching.jpg",
      },
      {
        id: 6,
        nombre: "Fotografia",
        subtitulo: "Cursos de Fotografia",
        descripcion:
          "El concepto audiovisual significa la integración e interrelación plena entre lo auditivo y lo visual para producir una nueva realidad o lenguaje. La percepción es simultánea. Se crean así nuevas realidades sentidos|sensoriales mediante mecanismos como la armonía, complementaria, refuerzo y contraste.",
        url: "/img/FOTOGRAFIA.jpg",
      },
      {
        id: 7,
        nombre: "Marketing y publicidad",
        subtitulo: "Cursos de Marketing y publicida",
        descripcion:
          "El concepto audiovisual significa la integración e interrelación plena entre lo auditivo y lo visual para producir una nueva realidad o lenguaje. La percepción es simultánea. Se crean así nuevas realidades sentidos|sensoriales mediante mecanismos como la armonía, complementaria, refuerzo y contraste.",
        url: "/img/MARKETING-Y-PUBLICIDAD.jpg",
      },
    ],
  }),

  watch: {
    loader() {
      const l = this.loader;
      this[l] = !this[l];

      setTimeout(() => (this[l] = false), 3000);

      this.loader = null;
    },
  },
};
</script>