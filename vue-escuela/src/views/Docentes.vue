<style>
.v-card--reveal {
  align-items: center;
  bottom: 0;
  justify-content: center;
  opacity: 0.9;
  position: absolute;
  width: 100%;
}
</style>

<template>
  <v-container >
    <v-layout wrap align-center justify-center>
                   <v-flex xs12 sm10 md6 lg4 xl3 yapaycolor--text>
  <h1 
          class="text-center font-weight-thin"
          style="font-family: 'Leckerli One', cursive ; font-size:3em; border-bottom:2px solid #FEC200"
        >Nuestros docentes</h1></v-flex></v-layout>
    <v-layout align-center justify-center wrap >
 
      <v-flex xs12 lg10  yapaycolor--text >
          
                <h1
          class="text-start  mt-5 mb-5 font-weight-thin"
          style="font-family: 'Leckerli One', cursive"
        >Marketing y publicidad</h1>
                    <!--=========================================================-->
        <v-divider></v-divider>

        <v-layout wrap  > 

 
          <!--=========================================================-->
          <v-flex v-for="marketingDocente in marketingDocentes" :key="marketingDocente.id" xs6 sm4 md3 lg3 xl3 pa-5>
              
            <v-hover v-slot="{ hover }">
              <v-card class="mx-auto fill-height " color="grey lighten-4" >
                <v-img :aspect-ratio="8 / 9" :src="marketingDocente.foto">
                  <v-expand-transition>
                    <div
                      v-if="hover"
                      class="
                        d-flex
                        transition-fast-in-fast-out
                        yapaycolor
                        pa-1
                        v-card--reveal
                        white--text
                      "
                      style="height: 100%"
                    >
                
                         {{ marketingDocente.nombre }}
                    </div>
                  </v-expand-transition>
                </v-img>

              </v-card>
            </v-hover>
          </v-flex>

      
        </v-layout>
        <v-divider></v-divider>
                  <!--=========================================================-->
                <h1
          class="text-start  mt-5 mb-5 font-weight-thin"
          style="font-family: 'Leckerli One', cursive"
        >Fotografía
        </h1>
                         <!--=========================================================-->
        <v-divider></v-divider>

        <v-layout wrap>

 
          <!--=========================================================-->
          <v-flex v-for="fotografiaDocente in fotografiaDocentes" :key="fotografiaDocente.id" xs6 sm4 md3 lg3 xl3 pa-5>
              
            <v-hover v-slot="{ hover }">
              <v-card class="mx-auto fill-height" color="grey lighten-4">
                <v-img :aspect-ratio="9 / 9" :src="fotografiaDocente.foto">
                  <v-expand-transition>
                    <div
                      v-if="hover"
                      class="
                        d-flex
                        transition-fast-in-fast-out
                        yapaycolor
                        pa-1
                        v-card--reveal
                        white--text
                      "
                      style="height: 100%"
                    >
                      {{ fotografiaDocente.nombre }}
                    </div>
                  </v-expand-transition>
                </v-img>

              </v-card>
            </v-hover>
          </v-flex>

      
        </v-layout>
                <v-divider></v-divider>

                  <!--=========================================================-->
               <!--=========================================================-->
               
                <h1
          class="text-start  mt-5 mb-5 font-weight-thin"
          style="font-family: 'Leckerli One', cursive"
        >Diseño grafico y audiovisual
        </h1>
                         <!--=========================================================-->
        <v-divider></v-divider>

        <v-layout wrap>

 
          <!--=========================================================-->
          <v-flex v-for="diseñoDocente in diseñoDocentes" :key="diseñoDocente.id" xs6 sm4 md3 lg3 xl3 pa-5>
              
            <v-hover v-slot="{ hover }">
              <v-card class="mx-auto fill-height" color="grey lighten-4">
                <v-img :aspect-ratio="9 / 9" :src="diseñoDocente.foto">
                  <v-expand-transition>
                    <div
                      v-if="hover"
                      class="
                        d-flex
                        transition-fast-in-fast-out
                        yapaycolor
                        pa-1
                        v-card--reveal
                        white--text
                      "
                      style="height: 100%"
                    >
                      {{ diseñoDocente.nombre }}
                    </div>
                  </v-expand-transition>
                </v-img>

              </v-card>
            </v-hover>
          </v-flex>

      
        </v-layout>
                <v-divider></v-divider>

                  <!--=========================================================-->
                       <!--=========================================================-->
                <h1
          class="text-start  mt-5 mb-5 font-weight-thin"
          style="font-family: 'Leckerli One', cursive"
        >Desarrollo web
        </h1>
                         <!--=========================================================-->
        <v-divider></v-divider>

        <v-layout wrap>

 
          <!--=========================================================-->
          <v-flex v-for="webDocente in webDocentes" :key="webDocente.id" xs6 sm4 md3 lg3 xl3 pa-5>
              
            <v-hover v-slot="{ hover }">
              <v-card class="mx-auto fill-height" color="grey lighten-4">
                <v-img :aspect-ratio="9 / 9" :src="webDocente.foto">
                  <v-expand-transition>
                    <div
                      v-if="hover"
                      class="
                        d-flex
                        transition-fast-in-fast-out
                        yapaycolor
                        pa-1
                        v-card--reveal
                        white--text
                      "
                      style="height: 100%"
                    >
                      {{ webDocente.nombre }}
                    </div>
                  </v-expand-transition>
                </v-img>

              </v-card>
            </v-hover>
          </v-flex>

      
        </v-layout>
                <v-divider></v-divider>

                  <!--=========================================================-->
                                 <!--=========================================================-->
                <h1
          class="text-start  mt-5 mb-5 font-weight-thin"
          style="font-family: 'Leckerli One', cursive"
        >Coaching y aprendizaje 
        </h1>
                         <!--=========================================================-->
        <v-divider></v-divider>

        <v-layout wrap>

 
          <!--=========================================================-->
          <v-flex v-for="coachDocente in coachDocentes" :key="coachDocente.id" xs6 sm4 md3 lg3 xl3 pa-5>
              
            <v-hover v-slot="{ hover }">
              <v-card class="mx-auto fill-height" color="grey lighten-4">
                <v-img :aspect-ratio="9 / 9" :src="coachDocente.foto">
                  <v-expand-transition>
                    <div
                      v-if="hover"
                      class="
                        d-flex
                        transition-fast-in-fast-out
                        yapaycolor
                        pa-1
                        v-card--reveal
                        white--text
                      "
                      style="height: 100%"
                    >
                      {{ coachDocente.nombre }}
                    </div>
                  </v-expand-transition>
                </v-img>

              </v-card>
            </v-hover>
          </v-flex>

      
        </v-layout>
                <v-divider></v-divider>

                  <!--=========================================================-->
      </v-flex>
    </v-layout>
    <v-container style="height: 8vh"> </v-container>
  </v-container>
</template>
<script>
export default {
  data: () => ({
    marketingDocentes: [
      {
        id: 1,
        foto:
          "https://yapaydigital.pe/wp-content/uploads/2021/08/New-Project-31-1-300x300.jpg",
        nombre: "BRUNO HELGUERO"
      },
      {
        id: 2,
        foto:
          "https://yapaydigital.pe/wp-content/uploads/2021/08/New-Project-2-300x300.jpg",
        nombre: "STEFANY RAMOS"
      },
      {
        id: 3,
        foto:
          "https://yapaydigital.pe/wp-content/uploads/2021/09/Danteazul-300x300.jpg",
        nombre: "DANTE LOAYZA"
      },

      {
        id: 4,
        foto:
          "https://yapaydigital.pe/wp-content/uploads/2021/08/New-Project-30-1-300x300.jpg",
        nombre: "ALVARO SÁNCHEZ"
      }
    ],
    fotografiaDocentes: [
      {
        id: 4,
        foto:
          "https://yapaydigital.pe/wp-content/uploads/2021/08/New-Project-32-1.jpg",
        nombre: "IVÁN URBINA"
      },

      {
        id: 8,
        foto:
          "https://yapaydigital.pe/wp-content/uploads/2021/08/New-Project-24-1-300x300.jpg",
        nombre: "ANTHONY RAMOS"
      },

      {
        id: 12,
        foto:
          "https://yapaydigital.pe/wp-content/uploads/2021/11/PerfilYapay-12-de-12-235x300.jpg",
        nombre: "ALEJANDRO REYES"
      }
    ],
    diseñoDocentes: [
      {
        id: 4,
        foto:
          "https://yapaydigital.pe/wp-content/uploads/2021/08/New-Project-32-1.jpg",
        nombre: "IVÁN URBINA"
      },
      {
        id: 5,
        foto:
          "https://yapaydigital.pe/wp-content/uploads/2021/08/New-Project-30-1-300x300.jpg",
        nombre: "ALVARO SÁNCHEZ"
      },
      {
        id: 6,
        foto:
          "https://yapaydigital.pe/wp-content/uploads/2021/08/New-Project-29-1-300x300.jpg",
        nombre: "ALEJANDRO COLAN"
      },

      {
        id: 8,
        foto:
          "https://yapaydigital.pe/wp-content/uploads/2021/08/New-Project-24-1-300x300.jpg",
        nombre: "ANTHONY RAMOS"
      },

      {
        id: 12,
        foto:
          "https://yapaydigital.pe/wp-content/uploads/2021/11/PerfilYapay-12-de-12-235x300.jpg",
        nombre: "ALEJANDRO REYES"
      }
    ],
    webDocentes: [
      {
        id: 9,
        foto:
          "https://yapaydigital.pe/wp-content/uploads/2021/08/New-Project-23-1-300x300.jpg",
        nombre: "D-LAND"
      },
      {
        id: 10,
        foto:
          "https://yapaydigital.pe/wp-content/uploads/2021/08/New-Project-27-1-300x300.jpg",
        nombre: "GABRIEL MARTINEZ"
      },
      {
        id: 11,
        foto:
          "https://yapaydigital.pe/wp-content/uploads/2021/08/New-Project-1-300x300.jpg",
        nombre: "ÁNGEL VEGA"
      },
      {
        id: 12,
        foto:
          "https://yapaydigital.pe/wp-content/uploads/2021/08/New-Project-34-1-300x300.jpg",
        nombre: "CARLOS JIMENEZ"
      }
    ],
    Docentes: [
      {
        id: 1,
        foto:
          "https://yapaydigital.pe/wp-content/uploads/2021/08/New-Project-31-1-300x300.jpg",
        nombre: "BRUNO HELGUERO"
      },
      {
        id: 2,
        foto:
          "https://yapaydigital.pe/wp-content/uploads/2021/08/New-Project-2-300x300.jpg",
        nombre: "STEFANY RAMOS"
      },
      {
        id: 3,
        foto:
          "https://yapaydigital.pe/wp-content/uploads/2021/09/Danteazul-300x300.jpg",
        nombre: "DANTE LOAYZA"
      },
      {
        id: 4,
        foto:
          "https://yapaydigital.pe/wp-content/uploads/2021/08/New-Project-32-1.jpg",
        nombre: "IVÁN URBINA"
      },
      {
        id: 5,
        foto:
          "https://yapaydigital.pe/wp-content/uploads/2021/08/New-Project-30-1-300x300.jpg",
        nombre: "ALVARO SÁNCHEZ"
      },
      {
        id: 6,
        foto:
          "https://yapaydigital.pe/wp-content/uploads/2021/08/New-Project-29-1-300x300.jpg",
        nombre: "ALEJANDRO COLAN"
      },
      {
        id: 7,
        foto:
          "https://yapaydigital.pe/wp-content/uploads/2021/08/New-Project-25-1-300x300.jpg",
        nombre: "GONZALO QUINTEROS"
      },
      {
        id: 8,
        foto:
          "https://yapaydigital.pe/wp-content/uploads/2021/08/New-Project-24-1-300x300.jpg",
        nombre: "ANTHONY RAMOS"
      },
      {
        id: 9,
        foto:
          "https://yapaydigital.pe/wp-content/uploads/2021/08/New-Project-23-1-300x300.jpg",
        nombre: "D-LAND"
      },
      {
        id: 10,
        foto:
          "https://yapaydigital.pe/wp-content/uploads/2021/08/New-Project-27-1-300x300.jpg",
        nombre: "GABRIEL MARTINEZ"
      },
      {
        id: 11,
        foto:
          "https://yapaydigital.pe/wp-content/uploads/2021/08/New-Project-1-300x300.jpg",
        nombre: "ÁNGEL VEGA"
      },
      {
        id: 12,
        foto:
          "https://yapaydigital.pe/wp-content/uploads/2021/11/PerfilYapay-12-de-12-235x300.jpg",
        nombre: "ALEJANDRO REYES"
      }
    ],
    coachDocentes: [
      {
        id: 3,
        foto:
          "https://yapaydigital.pe/wp-content/uploads/2021/09/Danteazul-300x300.jpg",
        nombre: "DANTE LOAYZA"
      },

      {
        id: 7,
        foto:
          "https://yapaydigital.pe/wp-content/uploads/2021/08/New-Project-25-1-300x300.jpg",
        nombre: "GONZALO QUINTEROS"
      }
    ]
  })
};
</script>