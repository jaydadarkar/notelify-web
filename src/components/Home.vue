<template>
  <v-app id="home">
    <v-app-bar
      app
      color="primary"
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

    <v-container fluid class="home">
        <v-row>
            <v-col
            cols=12
            md=1
            ></v-col>
            <v-col
            cols=12
            md=4
            >
            <v-form v-model="valid">
                <v-container>
                  <v-row>
                    <v-col
                      cols="12"
                    ></v-col>
                    <v-col
                      cols="12"
                    ></v-col>
                    <v-col
                      cols="12"
                    >
                      <v-text-field
                        full-width
                        append-icon="mdi-email"
                        v-model="email"
                        :rules="emailRules"
                        label="E-mail Id"
                        name="email"
                        required
                      ></v-text-field>
                      <v-text-field
                        full-width
                        v-model="password"
                        :append-icon="show1 ? 'mdi-eye' : 'mdi-eye-off'"
                        :rules="[rules.required, rules.min]"
                        :type="show1 ? 'text' : 'password'"
                        name="password"
                        label="Password"
                        hint="At least 8 characters"
                        counter
                        @click:append="show1 = !show1"
                      ></v-text-field>
                      <v-col
                      col=12 class="text-right pa-0">
                      <v-btn class="pa-0" color="#009688" text small>Forgot Your Password?</v-btn>
                      </v-col>
                      <br />
                      <v-row>
                        <v-col col=6>
                        <v-btn block class="mx-auto" color="#009688"><span class="text-white">Sign In</span></v-btn>
                        </v-col>
                        <v-col col=6>
                        <v-btn block class="mx-auto" color="#009688"><span class="text-white">Register</span></v-btn>
                        </v-col>
                      </v-row>
                    </v-col>
                  </v-row>
                </v-container>
              </v-form>
            </v-col>
            <v-col
            cols=12
            md=7
            >
            <h6 class="heading-1">Cross Platform</h6>
            <h1 class="heading-2">Notes App</h1>
            <br />
            <p class="paragraph">A cross platform notes keeping app.</p>
            <p class="paragraph">Reliable, fast and works accross</p>
            <p class="paragraph">Android, iPad, iPhone,</p>
            <p class="paragraph">and the Web.</p>
            </v-col>
        </v-row>
    </v-container>
  </v-app>
</template>

<script>
  export default {
    props: {
      source: String,
    },
    data: () => ({
      valid: false,
      email: '',
      password: '',
      show1: false,
      emailRules: [
        v => !!v || 'E-mail Id is required',
        v => /.+@.+/.test(v) || 'E-mail Id is invalid',
      ],
      rules: {
          required: value => !!value || 'Required.',
          min: v => v.length >= 8 || 'Min 8 characters',
          emailMatch: () => ('The email and password you entered don\'t match'),
        },      
    }),
  }
</script>

<style>
#home .v-navigation-drawer__border {
  display: none
}
.v-application--wrap{
  background-color: #009688 !important;
}
.text-white{
    color: #fff;
}
.home{
  background-image: url('../assets/cross-platform-notes-keeping-app.jpg');
  background-size: cover;
  height: 608px;
}
.heading-1{
  color: #444;
  font-size: 1rem;
  padding: 0px;
  margin: 0px;
  line-height: 0;
  padding-top: 10rem;
  padding-left: 5rem;
}
.heading-2{
  color: #444;
  font-size: 4rem;
  padding: 0px;
  margin: 0px;
  line-height: 1.2;
  padding-left: 5rem;
}
.paragraph{
  padding-left: 5rem;
  color: #444;
  margin: 0px !important;
}

@media screen and (max-width: 992px){
  .heading-1, .heading-2, .paragraph{
    color: white;
    padding-left: 1rem;
  }
}
</style>