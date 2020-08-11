<template>
  <v-app id="notes">
    <v-app-bar
      app
      clipped-left
      color="primary"
    >
      <v-app-bar-nav-icon @click="drawer = !drawer" color="white"></v-app-bar-nav-icon>
      <span class="title ml-3 mr-5"><v-icon color="white">mdi-pencil</v-icon> Notelify</span>

      <v-spacer></v-spacer>
    </v-app-bar>

    <v-navigation-drawer
      v-model="drawer"
      app
      clipped
      color="grey lighten-3"
    >
      <v-list
        dense
        class="grey lighten-3"
      >
        <v-list-item three-line>
            <v-list-item-content>
                <v-list-item-title>Three-line item</v-list-item-title>
                <v-list-item-subtitle>
                Secondary line text Lorem ipsum dolor sit amet,
                </v-list-item-subtitle>
                <v-list-item-subtitle>
                consectetur adipiscing elit.
                </v-list-item-subtitle>
            </v-list-item-content>
        </v-list-item>
        <v-divider color="black45"></v-divider>
        <v-list-item three-line>
            <v-list-item-content>
                <v-list-item-title>Three-line item</v-list-item-title>
                <v-list-item-subtitle>
                Secondary line text Lorem ipsum dolor sit amet,
                </v-list-item-subtitle>
                <v-list-item-subtitle>
                consectetur adipiscing elit.
                </v-list-item-subtitle>
            </v-list-item-content>
        </v-list-item>
        <v-divider color="black45"></v-divider>
        <v-list-item three-line>
            <v-list-item-content>
                <v-list-item-title>Three-line item</v-list-item-title>
                <v-list-item-subtitle>
                Secondary line text Lorem ipsum dolor sit amet,
                </v-list-item-subtitle>
                <v-list-item-subtitle>
                consectetur adipiscing elit.
                </v-list-item-subtitle>
            </v-list-item-content>
        </v-list-item>
        <v-divider color="black45"></v-divider>

      </v-list>
    </v-navigation-drawer>

    <v-main>
      <v-container
        fluid
        class="grey lighten-4 fill-height"
      >
        <v-row
          justify="center"
          align="center"
        >
        <p></p>
        </v-row>
      </v-container>
    </v-main>
  </v-app>
</template>

<script>
  export default {
    props: {
      source: String,
    },
    data: () => ({
      drawer: null,
      items: [
        { text: 'Reminders' },
      ],
    }),
  }
</script>

<style>
#notes .v-navigation-drawer__border {
  display: none
}
.title{
    color: white;
}
</style>