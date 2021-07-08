<template>
  <v-app>
    <v-app-bar
      app
      color="primary"
      dark
    >
      <div class="d-flex align-center">
        <v-img
          alt="Vuetify Logo"
          class="shrink mr-2"
          contain
          src="https://cdn.vuetifyjs.com/images/logos/vuetify-logo-dark.png"
          transition="scale-transition"
          width="40"
        />

        <h1>Edrafox</h1>
      </div>

      <v-spacer></v-spacer>

      <v-btn
        href="https://edrafox.com/index.html"
        target="_blank"
        text
      >
        <span class="mr-2">Saiba sobre nós</span>
        <v-icon>mdi-open-in-new</v-icon>
      </v-btn>
    </v-app-bar>

    <v-main>
      <v-container>
        <v-row>
          <v-col >
            <v-container>
              <div>
                <carousel></carousel>
              </div>
            </v-container>
          </v-col>
          <v-col>  
            <principal>     
            </principal>
          </v-col>  
        </v-row>   
      </v-container>
    </v-main>
  </v-app>
</template>

<script>
import principal from "./components/principal.vue"
import carousel from "./components/Carrosel.vue"

export default {
  name: 'App',

  components: {
    principal,
    carousel,
  },

  data: () => ({
    //
  }),
};
</script>

<style>
h1{
  position: relative;
}
.carrosel{
  width: 10%;
}
</style>
