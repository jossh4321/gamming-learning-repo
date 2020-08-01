<template>
  <v-container fluid>
    <v-row>
      <!--columna 1-->
      <v-row style="margin-right:7px">
        <v-col cols="12">
          <v-card width="inherit" min-height="750" class outlined>Hola 1</v-card>
        </v-col>
        <v-col cols="12">
          <v-card class="mx-auto" width="inherit" min-height="40px">
            <v-btn color="blue-grey" class="ma-2 white--text" width="inherit" height="40px">
              <v-icon right dark>mdi-gamepad-variant-outline</v-icon>
              <span style="margin-left:20px">Jugar Ahora!!</span>
            </v-btn>
          </v-card>
        </v-col>
      </v-row>

      <v-row>
        <v-col>
          <v-row>
            <v-col>
              <v-card class="item" outlined>
                <v-btn
                  color="blue-grey"
                  class="ma-2 white--text"
                  width="100%"
                  height="100%"
                  @click="cambiarValor()"
                >
                  <v-icon right dark>mdi-gamepad-variant-outline</v-icon>
                  <span style="margin-left:20px">Tienda</span>
                </v-btn>
                


              </v-card>
              <v-dialog v-model="dialogoTienda" >
                  <v-card width="500px" heigth="500px">
                    <v-card-title class="headline">Tienda</v-card-title>
                  </v-card>
                </v-dialog>
            </v-col>
            <v-col>
              <v-card class="item" outlined>
                <v-btn color="blue-grey" class="ma-2 white--text" width="100%" height="100%">
                  <v-icon right dark>mdi-gamepad-variant-outline</v-icon>
                  <span style="margin-left:20px">Heroes</span>
                </v-btn>
              </v-card>
            </v-col>
            <v-col>
              <v-card class="item" outlined>
                <v-btn color="blue-grey" class="ma-2 white--text" width="100%" height="100%">
                  <v-icon right dark>mdi-gamepad-variant-outline</v-icon>
                  <span style="margin-left:20px">Monedero</span>
                </v-btn>
              </v-card>
            </v-col>

            <!--v-col>
              <v-card class=" item" outlined>
                <v-btn color="blue-grey" class="ma-2 white--text" width="100%" height="100%">
                  <v-icon right dark>mdi-gamepad-variant-outline</v-icon>
                  <span style="margin-left:20px">Batallas</span>
                </v-btn>
              </v-card>
            </v-col-->
          </v-row>
        </v-col>
        <v-col cols="12">
          <v-card class="mx-auto" height="430px" outlined>
            <!--div  style="width:400px">
                <HeroItems></HeroItems>
            </div-->
          </v-card>
        </v-col>
        <v-col cols="12">
          <v-card class="mx-auto" outlined>
            <v-list nav dense>
              <v-subheader>Estadistica de el Heroe</v-subheader>

              <v-list-item-group v-model="item" color="primary">
                <v-list-item v-for="(item, i) in items" :key="i">
                  <v-list-item-icon>
                    <v-icon v-text="item.icon"></v-icon>
                  </v-list-item-icon>
                  <v-list-item-content style="margin-left:5px">
                    <v-list-item-title v-text="item.text"></v-list-item-title>
                  </v-list-item-content>
                  <v-list-item-content style="margin-left:5px">
                    <v-list-item-title v-text="item.score"></v-list-item-title>
                  </v-list-item-content>
                </v-list-item>
              </v-list-item-group>
            </v-list>
          </v-card>
        </v-col>
      </v-row>
    </v-row>

    

    <v-dialog v-model="dialogoMonedero" width="500px" heigth="500px">
      <v-card>
        <v-card-title class="headline">Monedero</v-card-title>
      </v-card>
    </v-dialog>

    <v-dialog v-model="dialogoHeroes" width="500px" heigth="500px">
      <v-card>
        <v-card-title class="headline">Heores</v-card-title>
      </v-card>
    </v-dialog>
  </v-container>
</template>
<script>
import HeroItems from "@/components/HeroItems.vue";
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
    };
  },
  methods:{
    cambiarValor: function(){
      this.dialogoTienda = true;
      console.log("Hice click");
    }
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
</style>
