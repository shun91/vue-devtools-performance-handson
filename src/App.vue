<template>
  <v-app id="app">
    <div>
      <img alt="Vue logo" src="./assets/logo.png" />
      <HelloWorld msg="Welcome to Your Vue.js + TypeScript App" />
      <heavy-dialog />
    </div>
  </v-app>
</template>

<script lang="ts">
import Vue from "vue";
import HelloWorld from "./components/HelloWorld.vue";
import HeavyDialog from "./components/HeavyDialog.vue";

export default Vue.extend({
  name: "app",
  components: {
    HelloWorld,
    HeavyDialog
  }
});
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
