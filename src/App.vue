<template>
  <v-app>
    <v-container text-xs-center>
      <v-layout wrap>
        <v-flex xs12><h1>vue-devtools-performance-handson</h1></v-flex>

        <v-flex xs12><heavy-dialog /></v-flex>

        <v-flex xs12><light-dialog /></v-flex>
      </v-layout>
    </v-container>
  </v-app>
</template>

<script lang="ts">
import Vue from "vue";
import HeavyDialog from "./components/HeavyDialog.vue";
import LightDialog from "./components/LightDialog.vue";

export default Vue.extend({
  components: { HeavyDialog, LightDialog }
});
</script>
