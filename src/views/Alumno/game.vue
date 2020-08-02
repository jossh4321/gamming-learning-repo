<template>
  <v-container fluid data-app>
    <v-row>
      <!--columna 1-->
      <v-col cols="5">
        <v-row style="margin-right:7px">
          <v-col cols="12">
            <v-card width="inherit" min-height="555" class="heroe1" outlined>Hola 1</v-card>
          </v-col>
          <v-col cols="12">
            <v-card class="mx-auto" width="inherit" min-height="70px">
              <v-btn color="blue-grey" class="ma-2 white--text" width="inherit" height="70px">
                <v-icon right dark>mdi-gamepad-variant-outline</v-icon>
                <span style="margin-left:20px">Jugar Ahora!!</span>
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
                        color="blue-grey"
                        class="ma-2 white--text"
                        width="100%"
                        height="100%"
                        @click="dialogoTienda = true"
                      >
                        <v-icon right dark>mdi-cart</v-icon>
                        <span style="margin-left:5px">Tienda</span>
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
                      >
                        <v-icon center dark>mdi-account-tie</v-icon>
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
                      >
                        <v-icon center dark>mdi-cart</v-icon>
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
                      >
                        <v-icon center dark>mdi-book-open-page-variant</v-icon>
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
                      >
                        <v-icon right dark>mdi-cash-multiple</v-icon>
                        <span style="margin-left:5px">Dinero</span>
                      </v-btn>
                    </v-card>
                  </v-col>
                </v-row>
              </v-col>
              <v-col cols="12">
                <v-card height="150px" outlined>
                  <v-card-title class="headline">Descripcion</v-card-title>
                  <v-card-subtitle>
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
                    <v-card height="100">Nivel 1</v-card>
                  </v-col>
                  <v-col cols="4">
                    <v-card height="100">Nivel 2</v-card>
                  </v-col>
                  <v-col cols="4">
                    <v-card height="100">Nivel 2</v-card>
                  </v-col>
                </v-row>
              </v-col>
              <v-col cols="12">
                <v-row>
                  <v-col cols="6">
                    <v-card width="inherit" height="350">
                      <v-col cols="12">
                        <v-card height="150">Misiones Diarias</v-card>
                      </v-col>
                      <v-col cols="12">
                        <v-card height="150">Mision Semanal</v-card>
                      </v-col>
                    </v-card>
                  </v-col>
                  <v-col cols="6">
                    <v-card width="inherit" height="300">
                      <v-list shaped>
                        <v-subheader>Ultimas Partidas Jugadas</v-subheader>
                        <v-list-item-group v-model="item" color="primary">
                          <v-list-item v-for="(item, i) in ultimasPartidas" :key="i">
                            <v-list-item-icon style="margin-right:10px">
                              <v-icon v-text="item.icon"></v-icon>
                            </v-list-item-icon>
                            <v-list-item-content>
                              <v-list-item-title v-text="item.fecha"></v-list-item-title>
                            </v-list-item-content>
                            <v-list-item-content>
                              <v-list-item-title v-text="item.resultado"></v-list-item-title>
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
      </v-card>
    </v-dialog>

    <v-dialog v-model="dialogoHeroes" width="500px" heigth="500px">
      <v-card>
        <v-card-title class="headline">Heores</v-card-title>
        <Heroes></Heroes>
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
      item: 1,
      items: [
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
