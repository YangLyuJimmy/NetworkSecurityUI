<template>
  <div>
    <v-card max-width=400px>
      <v-card-title> This is currently a blank page! </v-card-title>
      <v-btn @click="sendRequest">Test</v-btn>
      Test message is : {{ testMessage }}
    </v-card>
    <v-btn>one Button</v-btn>
  </div>
</template>

<script>
import Vue from "vue";

export default class Blank extends Vue{

  testMessage = "123";
  sendRequest() {
    fetch('/test', {
      method:'GET',
      mode: 'cors',
      headers: {
        'Content-Type': 'application/json'
      }
    })
    .then(response => response.json())
    .then( function(response) {
      //this.testMessage = response;
      console.log("I get the response!" + response)
    })
  }

}
</script>
