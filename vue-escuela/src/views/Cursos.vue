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
        mb-8
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
              <v-list-item-subtitle class="pr-6">
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
                      <v-btn class="mb-2" dark color="yapaycolor  " rounded>
                        <router-link
                          class="white--text text-decoration-none pa-5"
                          to="/contacto"
                          >Inscríbete</router-link
                        >
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
                              <div class="text-h4 mb-3">
                                {{ categoria.nombre }}
                              </div>
                              <v-img :src="categoria.url"></v-img>
                              <v-container mt-5>
                                <!-- <div class="text-h4 px-5">
                                {{ categoria.nombre }}
                              </div> -->
                                <v-container>
                                  <div>
                                    <p
                                      style="
                                        font-size: 18px;
                                        text-align: justify;
                                      "
                                    >
                                      {{ categoria.descripcion }}
                                    </p>
                                  </div>
                                </v-container>
                              </v-container>
                            </v-flex>

                            <v-flex xs12 lg6>
                              <!-- <div class="text-h4 px-5">
                                {{ categoria.nombre }}
                              </div>
                              <v-container pa-5>
                                <div>
                                  {{ categoria.descripcion }}
                                </div>
                              </v-container> -->
                              <v-container mt-10>
                                <div class="text-h4 mb-3 text-center">
                                  SOLICITA INFORMACIÓN Y <br />
                                  OBTÉN UN DESCUENTO
                                </div>
                                <iframe
                                  src="https://yapaydigital.pe/form/"
                                  width="100%"
                                  height="550"
                                  frameborder="0"
                                ></iframe>
                              </v-container>
                              <!-- <Form /> -->
                            </v-flex>
                          </v-layout>
                          <!-- <div class="text-h6 pa-5">
                            {{ categoria.descripcion }}
                          </div> -->
                        </v-card-text>

                        <v-card-actions class="justify-center">
                          <v-btn dark color="yapaycolor  " rounded>
                            <router-link
                              class="white--text text-decoration-none pa-5"
                              to="/contacto"
                              >Inscríbete</router-link
                            >
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
              max-width="25vw"
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

    <!-- <v-container style="height: 65vh"> -->
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
        descripcion:
          "Aprenderás a homologar y gestionar una cuenta de WhatsApp Business en un nivel experto con un Chatbot Inteligente. Empezando con la creación de flujos y la identificación de palabras clave para respuestas automáticas. Seguido de un catálogo de productos y manejo de base de datos. Finalmente, podrá gestionar campañas segmentando adecuadamente a su público objetivo, permitiéndole optimizar sus anuncios.",
        url: "img/cursos/CURSO-FACEBOOK-Y-WHATSAPP.jpg",
      },
      {
        id: 2,
        nombre: "Taller instagram",
        subtitulo: "taller de instagram",
        descripcion:
          "En el curso de Instagram Marketing para Empresas y Negocio, aprenderás el uso correcto de la plataforma de Instagram Business. Así como la metodología para la creación de contenido y el uso correcto de los hashtag. También, se realizarán acciones para crecer orgánicamente y se gestionarán anuncios con objetivo de ventas y conversiones de manera eficiente.",
        url: "img/cursos/TALLER-INSTAGRAM.jpg",
      },
      {
        id: 3,
        nombre: "Curso Community Manager",
        subtitulo: "curso community manager",
        descripcion:
          "El curso de Community Manager aprenderás a gestionar las redes sociales en un nivel experto, desarrollar un proyecto real con objetivos de venta, todo ello bajo una metodología dinámica teórico y práctica, con conocimientos en cápsulas específicos. Aprenderás a crear y optimizar un fanpage, conocer los diferentes tipos de publicaciones, entender las estadísticas y realizar informes, redacción creativa, contenido con tendencia viral, automatizar tus respuestas, homologar tus redes sociales, segmentar en un nivel avanzado, utilizar el píxel de Facebook, crear públicos personalizados y realizar campañas de remarketing, optimizar los anuncios en base a un ROI, tanto en Facebook como en Instagram.",
        url: "img/cursos/CURSO-COMMUNITY-MANAGER.jpg",
      },
      {
        id: 4,
        nombre: "Curso Google Analytics",
        subtitulo: "curso Google Analytics",
        descripcion:
          "Aprende a recopilar datos, analizarlos y realizar un informe que te ayude a optimizar tu sitio web. Entre ellos un blog de contenido, página corporativa, ecommerce y otros.",
        url: "img/cursos/GOOGLE-ANALYTICS.jpg",
      },
      {
        id: 5,
        nombre: "Curso Google Ads",
        subtitulo: "curso Google Ads",
        descripcion:
          "Realiza búsquedas de palabras clave, genera campañas, optimiza la inversión y certifícate en Google Adwords",
        url: "img/cursos/GOOGLE-ADS.jpg",
      },
      {
        id: 6,
        nombre: "Curso Branding",
        subtitulo: "curso Branding",
        descripcion:
          "En este curso obtendrás las herramientas para conocer las necesidades de tus clientes, crear estrategias de marketing y comunicación orientadas a posicionar tu marca en el mercado digital.",
        url: "img/cursos/CURSO-BRANDING.jpg",
      },
      {
        id: 7,
        nombre: "Curso Personal Branding",
        subtitulo: "curso Personal Branding",
        descripcion:
          "Tu marca personal es la puerta a tu carrera profesional. Decide cómo quieres que te perciban reclutadores, clientes y futuros aliados. Conoce todos los secretos detrás de crear y gestionar tu marca personal. Define y optimiza tus redes sociales, crea comunidades a través de una estrategia de contenido, y construye un portafolio que resalte en tu industria.",
        url: "img/cursos/PERSONAL-BRAND.jpg",
      },
      {
        id: 8,
        nombre: "Curso Creación de contenido para redes sociales",
        subtitulo: "curso Creación de contenido para redes sociales",
        descripcion:
          "El curso Marketing de contenidos, busca proporcionar conocimientos y técnicas creativas para la creación y difusión de diversos contenidos con la finalidad de generar engagement con las audiencias digitales.      Además, vas a poder entender cómo funcionan todas las redes sociales y el formato correcto para construir una comunidad de seguidores o futuros compradores; asimismo, medir y optimizar los resultados con estrategias y herramientas digitales para armar un plan de contenidos enfocados en los objetivos de la marca.¡Realiza tu propia estrategia de contenidos! Inscríbete ahora y conviértete en un experto en content marketing. Gestiona tus contenidos en social media, inbound marketing y todas las herramientas del marketing digital.",
        url: "img/cursos/CURSO-CREACION-DE-CONTENIDO-PARA-REDES-SOCIALES.jpg",
      },
      {
        id: 9,
        nombre: "Curso Photoshop Intermedio",
        subtitulo: "curso Photoshop Intermedio",
        descripcion:
          "Con el curso de Adobe Photoshop Intermedio aprenderás en corto tiempo el uso de las herramientas de uno de los mejores programas de diseñoy. ",
        url: "img/cursos/CURSO-PHOTOSHOP-INTERMEDIO.jpg",
      },
      {
        id: 10,
        nombre: "Curso Photoshop Avanzado",
        subtitulo: "curso Photoshop Avanzado",
        descripcion:
          "Aprende las técnicas imprescindibles para dar un salto cualitativo en tu flujo de trabajo y mejorar tus creaciones",
        url: "img/cursos/CURSO-PHOTOSHOP-AVANZADO.jpg",
      },
      {
        id: 11,
        nombre: "Curso Fotográfia y video",
        subtitulo: "curso Fotográfia y video",
        descripcion:
          "Aprende a crear contenido audiovisual impactante, desde las primeras ideas hasta la edición final, y explora el poder de las redes sociales. En este curso, aprenderás a crear contenidos visuales para publicarlos en las redes sociales, teniendo en cuenta técnicas de composición, escenografía y dirección. Fernando te mostrará cómo realizar el planteamiento de tu proyecto siguiendo una estética y aprovechando los recursos de las plataformas desde el primer momento.",
        url: "img/cursos/CURSO-DE-FOTO-Y-VIDEO.jpg",
      },
      {
        id: 11,
        nombre: "Curso Retoque fotográfico",
        subtitulo: "curso Retoque fotográfico",
        descripcion:
          "Domina acciones concretas del software de edición fotográfica por excelencia para procesar tus imágenes con resultados profesionales",
        url: "img/cursos/CURSO-DE-RETOQUE-FOTOGRTAFICO.jpg",
      },
      {
        id: 12,
        nombre: "Curso de video y Adobe Premiere",
        subtitulo: "curso de video y Adobe Premiere",
        descripcion:
          "Aprende a utilizar el software líder del sector desde cero y descubre cómo editar audio y vídeo de manera profesional",
        url: "img/cursos/CURSO-DE-VIDEO-Y-ADOBE-PREMIERE.jpg",
      },
      {
        id: 13,
        nombre: "Curso de After Effects",
        subtitulo: "curso de After Effects",
        descripcion:
          "Conoce a fondo todas las herramientas del programa referente en animación y video para mejorar tu flujo de trabajo, así como la calidad de tus proyectos",
        url: "img/cursos/CURSO-AFTER-EFFECTS.jpg",
      },
      {
        id: 14,
        nombre: "Curso de Desarrollo Front End",
        subtitulo: "curso de Desarrollo Front End",
        descripcion:
          "Domina las bases de HTML y CSS. Conoce la anatomía de un documento HTML, sus elementos y las propiedades de CSS. Maqueta las pantallas principales de tu página web con responsive design.",
        url: "img/cursos/CURSO-DE-DESARROLLO-FRONT-END.jpg",
      },
      {
        id: 15,
        nombre: "Curso de Desarrollo Back End",
        subtitulo: "curso de Desarrollo Back End",
        descripcion:
          "En este curso aprenderás todo lo necesario para montar tu propio servidor web, conocerás conceptos relacionados con la web en general pasando por el protocolo HTTP, que significa, para que nos sirve y como podemos utilizarlo en nuestros proyectos, también veremos todo lo relacionado con manejo de bases de datos para trabajar con información que provenga del frontend para trabajarlo con el backend enviandolo a una base de datos que nosotros tenemos",
        url: "img/cursos/CURSO-DE-DESARROLLO-BACK-END.jpg",
      },
      {
        id: 16,
        nombre: "Curso de Desarrollo de Apps Moviles",
        subtitulo: "curso de Desarrollo de Apps Moviles",
        descripcion:
          "En este curso aprenderás los conocimientos y bases para crear aplicaciones bridge con capacidad de despliegue tanto para Android como iOS, utilizando React Native, Javascript y un software de prototipado como Sketch o Adobe Xd. Te conectarás a APIs y aprenderás la capacidad de sync con Firebase o Realm db. Al finalizar este curso estarás en condiciones de desarrollar, implementar y desplegar tu propia aplicación móvil.",
        url: "img/cursos/CURSO-DESARROLLO-APP-MOBILES.jpg",
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