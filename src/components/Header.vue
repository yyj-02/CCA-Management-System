<template>
  <v-container class="text-h3 pb-0">
    {{ cca }}
  </v-container>
</template>

<script lang="ts">
import Vue from "vue";
export default Vue.extend({
  props: {
    cca: {
      default: "Volleyball",
    },
  },
});
</script>
