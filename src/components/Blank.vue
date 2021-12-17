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

export default{

  data: () => ({
    testMessage : "",
  }),
  methods: {
    sendRequest() {
      fetch('/test', {
        method:'GET',
        mode: 'cors',
        headers: {
          'Content-Type': 'application/json'
        }
      })
      .then( response => response.json())
      .then(data => {
        this.testMessage = data.msg;
        console.log("I get the response!" + data.msg);
      })
    }
  }

}
</script>
