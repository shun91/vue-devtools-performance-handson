<template>
  <v-dialog v-model="dialog" scrollable max-width="300px">
    <template #activator="{ on }">
      <v-btn v-on="on" dark>open heavy dialog</v-btn>
    </template>

    <v-card>
      <v-card-title>Select one</v-card-title>

      <v-divider />

      <v-card-text class="pa-0" style="height: 300px;">
        <v-radio-group v-model="selected">
          <v-list class="pa-0">
            <v-list-tile
              v-for="{ value } in items"
              :key="value"
              @click="selected = value"
              @mouseenter="updateOnmoused(value)"
              @mouseleave="updateOnmoused('')"
            >
              <v-list-tile-action>
                <v-radio :value="value" />
              </v-list-tile-action>

              <v-list-tile-content>
                <v-list-tile-title>{{ value }}</v-list-tile-title>
              </v-list-tile-content>
            </v-list-tile>
          </v-list>
        </v-radio-group>
      </v-card-text>

      <v-divider />

      <v-card-actions>
        <v-btn color="blue darken-1" flat @click="dialog = false">close</v-btn>
        <v-spacer />
        <span>{{ help }}</span>
      </v-card-actions>
    </v-card>
  </v-dialog>
</template>

<script lang="ts">
import Vue from "vue";

export default Vue.extend({
  data: () => ({
    dialog: false,
    selected: "",
    onmoused: ""
  }),

  computed: {
    items(): { value: string; help: string }[] {
      return new Array(500).fill(null).map((_, i) => ({
        value: `foo${i}`,
        help: `This is help for foo${i}`
      }));
    },

    help(): string {
      const item = this.items.find(({ value }) => value === this.onmoused);
      return item ? item.help : "";
    }
  },

  methods: {
    updateOnmoused(value: string) {
      this.onmoused = value;
    }
  }
});
</script>

<style scoped>
.v-input >>> .v-input__control {
  width: 100%;
}
</style>
