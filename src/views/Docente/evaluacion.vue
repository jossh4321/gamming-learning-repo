<template>
  <div>
    <h1>Evaluaciones</h1>
    <br>
    <br>
    <h3>Cursos:</h3>
    <v-expansion-panels
      v-model="panel"
      :readonly="readonly"
      multiple
    >
      <v-expansion-panel>
        <v-expansion-panel-header>Computación Grafica</v-expansion-panel-header>
        <v-expansion-panel-content>
          Ir al grupo del curso
          <v-btn style="float:right;">Ir al Curso</v-btn>
        </v-expansion-panel-content>
      </v-expansion-panel>

      <v-expansion-panel>
        <v-expansion-panel-header>Diseño de Interfaces</v-expansion-panel-header>
        <v-expansion-panel-content>
          Ir al grupo del curso
          <v-btn style="float:right;">Ir al Curso</v-btn>
        </v-expansion-panel-content>
      </v-expansion-panel>

      <v-expansion-panel>
        <v-expansion-panel-header>Base de datos I</v-expansion-panel-header>
        <v-expansion-panel-content>
          Ir al grupo del curso
          <v-btn style="float:right;">Ir al Curso</v-btn>
        </v-expansion-panel-content>
      </v-expansion-panel>
    </v-expansion-panels>
  </div>
</template>
<script>
  export default {
    data: () => ({
      panel: [0, 1],
      readonly: false,
    }),
  }
</script>