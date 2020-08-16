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
      <v-btn text><v-icon color="white">mdi-plus</v-icon></v-btn>
      <v-btn @click="logout()" text><v-icon color="white">mdi-power</v-icon></v-btn>
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
        <v-list-item>
          <v-row>
            <v-col
            cols=6 class="p-0 text-left">
            Notes Title
            </v-col>
            <v-col
            cols=6 class="p-0 text-right">
              <v-btn text small><v-icon color="teal">mdi-pencil</v-icon></v-btn>
              <v-btn text small><v-icon color="teal">mdi-delete</v-icon></v-btn>
            </v-col>
            <v-col
            cols=12 class="p-0 text-left">
            <small>Created At:- 29/12/2019 11:50<br />
            Updated At:- 29/12/2019 11:50</small>
            </v-col>            
          </v-row>
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
import router from '../router/index'
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
    methods: {
      logout(){
        router.go(-1);
      }
    }
  }
</script>

<style>
#notes .v-navigation-drawer__border {
  display: none
}
.title{
    color: white;
}
.p-0{
  padding: 5px !important;
}
</style>