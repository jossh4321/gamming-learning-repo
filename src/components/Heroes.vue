<template>
  <v-container >
    <v-data-iterator
      :items="items"
      :items-per-page.sync="itemsPerPage"
      hide-default-footer
    >
      <template v-slot:header>
        <v-toolbar
          class="mb-2"
          color="indigo darken-5"
          dark
          flat
        >
          <v-toolbar-title>This is a header</v-toolbar-title>
        </v-toolbar>
      </template>

      <template v-slot:default="props">
        <v-row>
          <v-col
            v-for="item in props.items"
            :key="item.name"
            cols="12"
            sm="6"
            md="4"
            lg="3"
          >
            <v-card>
              <v-card-title class="subheading font-weight-bold">{{ item.name }}</v-card-title>

              <v-divider></v-divider>

              <v-list dense>
                <v-list-item>
                  <v-list-item-content>Sharpness:</v-list-item-content>
                  <v-list-item-content class="align-end">{{ item.Sharpness }}</v-list-item-content>
                </v-list-item>

                <v-list-item>
                  <v-list-item-content>Weigth:</v-list-item-content>
                  <v-list-item-content class="align-end">{{ item.Weigth }}</v-list-item-content>
                </v-list-item>

                <v-list-item>
                  <v-list-item-content>Hardness:</v-list-item-content>
                  <v-list-item-content class="align-end">{{ item.hardness }}</v-list-item-content>
                </v-list-item>

                <v-list-item>
                  <v-list-item-content>Gauntlet:</v-list-item-content>
                  <v-list-item-content class="align-end">{{ item.Gauntlet }}</v-list-item-content>
                </v-list-item>
              </v-list>
            </v-card>
          </v-col>
        </v-row>
      </template>
    </v-data-iterator>
  </v-container>
</template>
<script>
  export default {
    name: "Heroes",  
    data: () => ({
      itemsPerPage: 4,
      items: [
        {
          name: 'Sword',
          Sharpness: 240,
          Weigth: 720,
          hardness: 257,
          Damage: 400
        },
        {
          name: 'Helmet',
          Sharpness: 235,
          Weigth: 437,
          hardness: 643,
          Damage: 875
        },
        {
          name: 'Shield',
          Sharpness: 453,
          Weigth: 732,
          hardness: 794,
          Damage: 456
        },
        {
          name: 'Gauntlet',
          Sharpness: 654,
          Weigth: 123,
          hardness: 877,
          Damage: 673
        },
        /*{
          name: 'Neckless',
          Sharpness: 134,
          Weigth: 789,
          hardness: 456,
          Damage: 789
        },*/
      ],
    }),
  }
</script>