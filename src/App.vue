<template>
  <v-app>
    <v-app-bar
      app
      color="#009688"
      dark
    >
      <div class="d-flex align-center">
        <v-icon>mdi-pencil</v-icon>
      <v-btn
        href="https://www.notelify.co/"
        target="_blank"
        text
      >
        <span>Notelify</span>
      </v-btn>

      </div>

      <v-spacer></v-spacer>

    </v-app-bar>

    <v-main>
      <HelloWorld/>
    </v-main>
  </v-app>
</template>

<script>
import HelloWorld from './components/HelloWorld';

export default {
  name: 'App',

  components: {
    HelloWorld,
  },

  data: () => ({
    //
  }),
};
</script>
