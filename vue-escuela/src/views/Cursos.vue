<style>
@import url("https://fonts.googleapis.com/css2?family=Leckerli+One&display=swap");
</style>
<template>
  <v-container>
    <v-layout justify-center>
      <v-flex class="display-1 pa-5 mb-5 mt-5" yapaycolor--text>
        <h1
          class="text-center font-weight-thin"
          style="font-family: 'Leckerli One', cursive"
        >
          Cursos
        </h1></v-flex
      ></v-layout
    >
    <v-spacer></v-spacer>

    <v-layout wrap>
      <v-flex v-for="categoria in categorias" xs3 mb-5 :key="categoria.id">
        <v-card class="mt-5" max-width="344">
          <v-img :src="categoria.url" height="200px"></v-img>

          <v-card-title> {{ categoria.nombre }} </v-card-title>

          <v-card-subtitle> {{ categoria.subtitulo }}</v-card-subtitle>

          <v-card-actions> </v-card-actions>
        </v-card>
      </v-flex>
    </v-layout>
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
        nombre: "Audivisual",
        subtitulo: "Cursos de audivisual",
        descripcion:
          "El concepto audiovisual significa la integración e interrelación plena entre lo auditivo y lo visual para producir una nueva realidad o lenguaje. La percepción es simultánea. Se crean así nuevas realidades sentidos|sensoriales mediante mecanismos como la armonía, complementaria, refuerzo y contraste.",
        url: "/img/audi.jpg",
      },
      {
        id: 5,
        nombre: "Audivisual",
        subtitulo: "Cursos de audivisual",
        descripcion:
          "El concepto audiovisual significa la integración e interrelación plena entre lo auditivo y lo visual para producir una nueva realidad o lenguaje. La percepción es simultánea. Se crean así nuevas realidades sentidos|sensoriales mediante mecanismos como la armonía, complementaria, refuerzo y contraste.",
        url: "/img/audi.jpg",
      },
      {
        id: 5,
        nombre: "Audivisual",
        subtitulo: "Cursos de audivisual",
        descripcion:
          "El concepto audiovisual significa la integración e interrelación plena entre lo auditivo y lo visual para producir una nueva realidad o lenguaje. La percepción es simultánea. Se crean así nuevas realidades sentidos|sensoriales mediante mecanismos como la armonía, complementaria, refuerzo y contraste.",
        url: "/img/audi.jpg",
      },
      {
        id: 5,
        nombre: "Audivisual",
        subtitulo: "Cursos de audivisual",
        descripcion:
          "El concepto audiovisual significa la integración e interrelación plena entre lo auditivo y lo visual para producir una nueva realidad o lenguaje. La percepción es simultánea. Se crean así nuevas realidades sentidos|sensoriales mediante mecanismos como la armonía, complementaria, refuerzo y contraste.",
        url: "/img/audi.jpg",
      },
      {
        id: 5,
        nombre: "Audivisual",
        subtitulo: "Cursos de audivisual",
        descripcion:
          "El concepto audiovisual significa la integración e interrelación plena entre lo auditivo y lo visual para producir una nueva realidad o lenguaje. La percepción es simultánea. Se crean así nuevas realidades sentidos|sensoriales mediante mecanismos como la armonía, complementaria, refuerzo y contraste.",
        url: "/img/audi.jpg",
      },
    ],
  }),
};
</script>