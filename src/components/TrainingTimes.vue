<template>
  <v-container>
    <v-card class="rounded-xl" elevation="4" height="100%" width="100%">
      <v-card-title class="headline font-weight-medium">
        Training Times
      </v-card-title>
      <v-card-text>
        <v-list>
          <v-list-item
            v-for="(trainingTime, index) in trainingTimes"
            :key="index"
          >
            <v-list-item-content>
              <v-list-item-title
                class="font-weight-regular title"
                v-text="trainingTime.day"
              ></v-list-item-title>
              <v-list-item-subtitle
                v-text="trainingTime.startTime + ' - ' + trainingTime.endTime"
              ></v-list-item-subtitle>
            </v-list-item-content>
          </v-list-item>
        </v-list>
      </v-card-text>
    </v-card>
  </v-container>
</template>

<script lang="ts">
import Vue from "vue";
export default Vue.extend({
  props: {
    trainingTimes: {
      default: [
        { day: "Monday", startTime: "5pm", endTime: "7pm" },
        { day: "Wednesday", startTime: "9pm", endTime: "11pm" },
      ],
    },
  },
});
</script>
