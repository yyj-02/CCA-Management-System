<template>
  <v-container class="text-h3 pb-0">
    <v-container class="py-0 d-none d-lg-block">
      {{ cca }}
    </v-container>
    <v-container class="d-flex d-lg-none justify-space-between align-center">
      <v-container class="pa-0">{{ cca }}</v-container>
      <v-btn outlined fab color="deep-purple" @click="toggleNav">
        <v-icon>mdi-format-list-bulleted-square</v-icon>
      </v-btn>
    </v-container>
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
  methods: {
    toggleNav: function () {
      this.$emit("toggle-nav");
    },
  },
});
</script>
