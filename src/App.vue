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

        <v-img
          alt="Vuetify Name"
          class="shrink mt-1 hidden-sm-and-down"
          contain
          min-width="100"
          src="https://cdn.vuetifyjs.com/images/logos/vuetify-name-dark.png"
          width="100"
        />
      </div>

      <v-spacer></v-spacer>

    </v-app-bar>

    <v-main>
      <v-container fluid class="list">
        <v-row no-gutters>
          
            <v-btn color=primary @click="showHello = true; showBlank = false">Show HelloWorld</v-btn>
          
          
            <v-btn color=secondary @click="showBlank = true; showHello = false">Show Blank</v-btn>
          
          
        </v-row>
        
      </v-container>
      

      <div v-show="showHello">
        <HelloWorld/>
      </div>

      <div v-show="showBlank">
        <Blank/>
      </div>

      
    </v-main>
  </v-app>
</template>

<script>
import HelloWorld from './components/HelloWorld';
import Blank from './components/Blank';

export default {
  name: 'App',

  components: {
    HelloWorld,
    Blank,
  },

  data: () => ({
    showHello : false,
    showBlank : false,
    //
  }),
};
</script>


<style>
.list {
  overflow: auto;
  flex: 1 1 10px;
}
.v-btn_content {
  text-decoration-color: white;
}
</style>