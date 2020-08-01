<template>
  <v-container fluid>
    <v-row>
      <!--columna 1-->
      <v-row style="margin-right:7px">
        <v-col cols="12">
          <v-card width="inherit" min-height="700" class outlined>Hola 1</v-card>
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
        <v-col cols="12">
          <v-card class="mx-auto" width="inherit" outlined>Hola 1</v-card>
        </v-col>
        <v-col cols="12">
          <v-card class="mx-auto" max-width="inherit" outlined>Hola 2</v-card>
        </v-col>
        <v-col cols="12">
          <v-card class="mx-auto" max-width="inherit" outlined>
            <v-list disabled>
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
  </v-container>
</template>
<script>
export default {
  name: "game",
  data: () => ({
    item: 1,
    items: [
      { text: "Fuerza", icon: "mdi-clock" , score:789},
      { text: "Habilidad", icon: "mdi-account" , score:1790},
      { text: "Salud", icon: "mdi-flag" , score:10000},
      { text: "Especial", icon: "mdi-clock" , score:4567},
      { text: "Furia", icon: "mdi-account", score:1230 },
      { text: "Velocidad", icon: "mdi-flag" , score:1980},
    ],
  }),
};
</script>
<style scoped>
.cont {
  display: flex;
  flex-direction: column;
  height: 1000px;
}
</style>
