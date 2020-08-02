<template>
  <v-container fluid data-app>
    <v-row>
      <!--columna 1-->
      <v-col cols="5">
        <v-row style="margin-right:7px">
          <v-col cols="12">
            <v-card width="inherit" min-height="555" class="heroe1" outlined></v-card>
          </v-col>
          <v-col cols="12">
            <v-card class="mx-auto" width="inherit" min-height="70px">
              <v-btn color="blue-grey" class="ma-2 white--text" width="inherit" height="70px"
              style="background:#4d4d4d">
                <v-icon right style="color:white">mdi-gamepad-variant-outline</v-icon>
                <span style="margin-left:20px; color:white">Jugar Ahora!!</span>
              </v-btn>
            </v-card>
          </v-col>
        </v-row>
      </v-col>

      <v-col cols="7">
        <v-row>
          <v-col cols="4">
            <v-card height="100%" outlined width="inherit" class="card3">
              <v-card-title style="color:white">Items del Heroe</v-card-title>
              <v-card height="180px" style="margin:15px" class="sword"></v-card>
              <v-card height="180px" style="margin:15px" class="sword2"></v-card>
              <v-card height="180px" style="margin:15px" class="sword"></v-card>
              <v-card height="180px" style="margin:15px" class="sword"></v-card>
            </v-card>
          </v-col>
          <v-col cols="8">
          <v-card outlined style="padding:15px"  class="card4">
            <v-row>
              <v-col cols="12">
                <v-row>
                  <v-col cols="3">
                    <v-card height="50">
                      <v-btn
                        class="ma-2 white--text"
                        width="100%"
                        height="100%"
                        @click="dialogoTienda = true"
                        style="background:#4d4d4d"
                      >
                        <v-icon right style="color:white">mdi-cart</v-icon>
                        <span style="margin-left:5px;color:white">Tienda</span>
                      </v-btn>
                    </v-card>
                  </v-col>
                  <v-col cols="2">
                    <v-card height="50">
                      <v-btn
                        color="blue-grey"
                        class="ma-2 white--text"
                        width="100%"
                        height="100%"
                        @click="dialogoTienda = true"
                        style="background:#4d4d4d"
                      >
                        <v-icon center style="color:white">mdi-account-tie</v-icon>
                      </v-btn>
                    </v-card>
                  </v-col>
                  <v-col cols="2">
                    <v-card height="50">
                      <v-btn
                        color="blue-grey"
                        class="ma-2 white--text"
                        width="100%"
                        height="100%"
                        @click="dialogoTienda = true"
                        style="background:#4d4d4d"
                      >
                        <v-icon center style="color:white">mdi-cart</v-icon>
                      </v-btn>
                    </v-card>
                  </v-col>
                  <v-col cols="2">
                    <v-card height="50">
                      <v-btn
                        color="blue-grey"
                        class="ma-2 white--text"
                        width="100%"
                        height="100%"
                        @click="dialogoTienda = true"
                        style="background:#4d4d4d"
                      >
                        <v-icon center style="color:white">mdi-book-open-page-variant</v-icon>
                      </v-btn>
                    </v-card>
                  </v-col>
                  <v-col cols="3">
                    <v-card height="50">
                      <v-btn
                        color="blue-grey"
                        class="ma-2 white--text"
                        width="100%"
                        height="100%"
                        @click="dialogoTienda = true"
                        style="background:#4d4d4d"
                      >
                        <v-icon right style="color:white">mdi-cash-multiple</v-icon>
                        <span style="margin-left:5px;color:white;">Dinero</span>
                      </v-btn>
                    </v-card>
                  </v-col>
                </v-row>
              </v-col>
              <v-col cols="12">
                <v-card height="150px"  class="descripcion">
                  <v-card-title class="headline" style="color:white">Descripcion</v-card-title>
                  <v-card-subtitle style="color:white" >
                    Este heroe te permite paralizar a tus enemigos e incrementar
                    la fuerza de tus alidos ademas de recuperar vida, es un heore de soporte muy poderoso
                    en batallas por equipos
                  </v-card-subtitle>
                </v-card>
              </v-col>
              <v-col cols="12">
                <h4 style="color:white">Niveles Alcanzados esta semana</h4>
                <v-row>
                  <v-col cols="4">
                    <v-card height="100" class="level">Nivel 1</v-card>
                  </v-col>
                  <v-col cols="4">
                    <v-card height="100" class="level">Nivel 2</v-card>
                  </v-col>
                  <v-col cols="4">
                    <v-card height="100" class="level">Nivel 2</v-card>
                  </v-col>
                </v-row>
              </v-col>
              <v-col cols="12">
                <v-row>
                  <v-col cols="6">
                    <v-card width="inherit" height="350" style="background:#404040">
                      <v-col cols="12">
                        <v-card height="150" style="color:white"  class="misiones">Misiones Diarias</v-card>
                      </v-col>
                      <v-col cols="12">
                        <v-card height="150" style="color:white" class="misiones">Mision Semanal</v-card>
                      </v-col>
                    </v-card>
                  </v-col>
                  <v-col cols="6">
                    <v-card width="inherit" height="300" style="background:#4d4d4d" >
                      <v-list shaped style="background:#4d4d4d" >
                        <v-subheader style="color:white">Ultimas Partidas Jugadas</v-subheader>
                        <v-list-item-group v-model="item" color="primary">
                          <v-list-item v-for="(item, i) in ultimasPartidas" :key="i">
                            <v-list-item-icon style="margin-right:10px;color:white">
                              <v-icon v-text="item.icon"></v-icon>
                            </v-list-item-icon>
                            <v-list-item-content>
                              <v-list-item-title style="color:white" v-text="item.fecha"></v-list-item-title>
                            </v-list-item-content>
                            <v-list-item-content>
                              <v-list-item-title style="color:white" v-text="item.resultado"></v-list-item-title>
                            </v-list-item-content>
                          </v-list-item>
                        </v-list-item-group>
                      </v-list>
                    </v-card>
                  </v-col>
                </v-row>
              </v-col>
            </v-row>

            </v-card>


          </v-col>
        </v-row>
      </v-col>
    </v-row>
    <v-dialog v-model="dialogoMonedero" width="500px" heigth="500px">
      <v-card>
        <v-card-title class="headline">Monedero</v-card-title>
          <v-card-actions>
            <v-spacer></v-spacer>
            <v-col>
              <v-btn color="green darken-1" @click="dialogoMonedero = false">Aceptar</v-btn>
            </v-col>
            <v-col>
              <v-btn color="green darken-1" @click="dialogoMonedero = false">Cancelar</v-btn>
            </v-col>
          </v-card-actions>
      </v-card>
    </v-dialog>

    <v-dialog v-model="dialogoHeroes" width="500px" heigth="500px">
      <v-card>
        <v-card-title class="headline">Heores</v-card-title>
        <v-card-actions>
            <v-spacer></v-spacer>
            <v-col>
              <v-btn color="green darken-1" @click="dialogoHeroes = false">Aceptar</v-btn>
            </v-col>
            <v-col>
              <v-btn color="green darken-1" @click="dialogoHeroes = false">Cancelar</v-btn>
            </v-col>
          </v-card-actions>
      </v-card>
    </v-dialog>
  </v-container>
</template>
<script>
import HeroItems from "@/components/HeroItems.vue";
import Heroes from "@/components/Heroes.vue";
export default {
  name: "game",
  components: {
    HeroItems,
  },
  data() {
    return {
      itemsPerPAge:1,
      item: 1,
      items: [
        {
          name: 'Frozen Yogurt',
          calories: 159,
          fat: 6.0,
          carbs: 24,
          protein: 4.0,
          sodium: 87,
          calcium: '14%',
          iron: '1%',
        },
        { text: "Strength", icon: "mdi-clock", score: 789 },
        { text: "Skills", icon: "mdi-account", score: 1790 },
        { text: "Health", icon: "mdi-flag", score: 10000 },
        { text: "Special", icon: "mdi-clock", score: 4567 },
        { text: "Anger", icon: "mdi-account", score: 1230 },
        { text: "Speed", icon: "mdi-flag", score: 1980 },
      ],
      dialogoTienda: false,
      dialogoMonedero: false,
      dialogoHeroes: false,
      dialog: false,
      ultimasPartidas: [
        {
          fecha: "02/08/2020",
          icon: "mdi-gamepad-variant-outline",
          resultado: "Victoria",
        },
        {
          fecha: "30/07/2020",
          icon: "mdi-gamepad-variant-outline",
          resultado: "Victoria",
        },
        {
          fecha: "28/07/2020",
          icon: "mdi-gamepad-variant-outline",
          resultado: "Derrota",
        },
        {
          fecha: "26/07/2020",
          icon: "mdi-gamepad-variant-outline",
          resultado: "Derrota",
        }
      ],
    };
  },
};
</script>
<style scoped>
.cont {
  display: flex;
  flex-direction: column;
  height: 1000px;
}
.item {
  flex-basis: 20%;
  height: 60px;
}
.cont2 {
  display: flex;
  flex-direction: row;
}


</style>
