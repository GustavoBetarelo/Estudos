<template>
  <v-container class="pa-4 d-flex" style="min-height: 100vh" fluid>
    <v-layout class="flex-fill container-landing rounded-xl" column>
      <div class="col-12 mx-auto flex-fill d-flex flex-column">
        <!-- Top Bar -->
        <v-flex
          shrink
          class=" col-12 justify-space-between align-center mx-auto mt-2 pa-4 top-bar-desing rounded-xl"
        >
          <v-layout>
            <v-flex>
              <v-container fluid class="pa-0" grid-list-xl>
                <v-layout align-center justify-center>
                  <v-flex class="hidden-xs-only" shrink>
                    <h6 class="text-h5 font-weight-bold">
                      Girabel's Enterprise
                    </h6>
                  </v-flex>

                  <v-flex class="hidden-xs-only" shrink>
                    <v-text-field
                      hide-details
                      prepend-inner-icon="mdi-magnify"
                      class="font-weight-bold"
                      placeholder="Search"
                      filled
                      rounded
                      dense
                    ></v-text-field>
                  </v-flex>

                  <v-flex class="hidden-xs-only" shrink>
                    <h4>Inicio</h4>
                  </v-flex>

                  <v-flex class="hidden-xs-only " shrink>
                    <h4>Empresa</h4>
                  </v-flex>

                  <v-flex class="hidden-xs-only " shrink>
                    <h4>Serviços</h4>
                  </v-flex>

                  <v-flex class="hidden-xs-only " shrink>
                    <v-btn
                      color="primary"
                      elevation="0"
                      dark
                      rounded
                      large
                      @click="openLogin"
                    >
                      Entrar
                    </v-btn>
                  </v-flex>
                </v-layout>
              </v-container>
            </v-flex>
          </v-layout>

          <v-flex class="pa-4">
            <v-btn @click="marcas">Listar Marcas</v-btn>

            <v-simple-table class="pa-4 mt-4">
              <template v-slot:default>
                <thead>
                  <tr>
                    <th class="text-center font-weight-bold text-h6">
                      Vai ter dados aqui
                    </th>
                    <th class="text-center font-weight-bold text-h6">
                      Confia pai
                    </th>
                  </tr>
                </thead>
                <tbody>
                  <tr
                    class="text-center"
                    v-for="item in desserts"
                    :key="item.name"
                  >
                    <td>{{ item.name }}</td>
                    <td>{{ item.calories }}</td>
                  </tr>
                </tbody>
              </template>
            </v-simple-table>
          </v-flex>
        </v-flex>
      </div>
    </v-layout>
  </v-container>
</template>

<script>
import api from "@/services/api";
export default {
  name: "home",

  data: () => ({
    desserts: [
      {
        name: "Frozen Yogurt",
        calories: 159,
      },
      {
        name: "Ice cream sandwich",
        calories: 237,
      },
      {
        name: "Eclair",
        calories: 262,
      },
      {
        name: "Cupcake",
        calories: 305,
      },
      {
        name: "Gingerbread",
        calories: 356,
      },
      {
        name: "Jelly bean",
        calories: 375,
      },
      {
        name: "Lollipop",
        calories: 392,
      },
      {
        name: "Honeycomb",
        calories: 408,
      },
      {
        name: "Donut",
        calories: 452,
      },
      {
        name: "KitKat",
        calories: 518,
      },
    ],
  }),

  methods: {
    async marcas() {
      try {
        const response = await api.get("/butterfree");
        console.log(response);
      } catch (error) {
        console.log(error);
      }
    },
  },
};
</script>

<style scoped>
.top-bar-desing {
  background-image: linear-gradient(to right, #9696a0, rgba(0, 0, 0, 0.1));
}

.border-default {
  backdrop-filter: blur(20px);
  border: 1px solid rgba(238, 238, 238, 0.5);
}
</style>
