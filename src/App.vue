<template>
  <v-app id="app">
    <v-main>
      <home />
    </v-main>
  </v-app>
</template>

<script>
import home from "./components/pages/home/index";

export default {
  name: "App",

  components: {
    home,
  },

  data: () => ({
    //
  }),
};
</script>
