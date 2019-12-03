<template>
  <v-list-tile
    ripple
    @click="$emit('click')"
    @mouseenter="$emit('mouseenter')"
    @mouseleave="$emit('mouseleave')"
  >
    <v-list-tile-action>
      <v-radio :value="item.value" />
    </v-list-tile-action>

    <v-list-tile-content>
      <v-list-tile-title>{{ item.value }}</v-list-tile-title>
    </v-list-tile-content>
  </v-list-tile>
</template>

<script lang="ts">
import Vue, { PropType } from "vue";

export default Vue.extend({
  props: { item: { type: Object as PropType<any>, required: true } }
});
</script>
