<template>
  <v-container>
    <v-card class="rounded-xl" elevation="2" height="100%" width="100%">
      <v-card-title class="headline font-weight-medium">
        Players Cut
      </v-card-title>
      <v-card-text>
        <v-list>
          <template v-for="(currentPlayer, index) in currentPlayers">
            <v-list-item
              class="text-decoration-line-through"
              v-if="currentPlayer.cut"
              :key="index"
              @click="toggleCut(index)"
            >
              {{ currentPlayer.name }}
            </v-list-item>
            <v-list-item
              class="purple lighten-4"
              v-else
              :key="index"
              @click="toggleCut(index)"
            >
              {{ currentPlayer.name }}
            </v-list-item>
          </template>
        </v-list>
        <v-row>
          <v-col>
            <v-btn block rounded @click="clearCut"> Clear </v-btn>
          </v-col>
          <v-col>
            <v-btn color="purple lighten-3" block rounded @click="submitCut">
              Submit
            </v-btn>
          </v-col>
        </v-row>
      </v-card-text>
    </v-card>
  </v-container>
</template>

<script lang="ts">
import Vue from "vue";
export default Vue.extend({
  props: {
    currentPlayers: {
      default: [
        { name: "Yeoh Yong Jie", cut: false },
        { name: "John Doe", cut: true },
        { name: "Yuvaraj Kumaresan", cut: false },
      ],
    },
  },
  methods: {
    toggleCut: function (index: number) {
      this.$emit("toggle-cut", index);
    },
    clearCut: function () {
      this.$emit("clear-cut");
    },
    submitCut: function () {
      this.$emit("submit-cut");
    },
  },
});
</script>
