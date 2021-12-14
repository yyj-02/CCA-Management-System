<template>
  <v-container>
    <v-card id="grad" class="rounded-xl" elevation="2" height="200%" width="100%">
      <v-card-title class="justify-center headline white--text font-weight-medium"> Days To {{ eventDetails.eventName }} </v-card-title>
      <v-card-text class="font-weight-black white--text text-center display-4">
        {{ eventDetails. daysToEvent }}
      </v-card-text>
    </v-card>
  </v-container>
</template>

<script lang="ts">
import Vue from 'vue'
export default Vue.extend({
  props: {
    eventDetails: {
      default: {
        eventName: "IHG",
        daysToEvent: 6
      }
    },
  },
})
</script>
<style>
#grad {
  background-image: linear-gradient(to bottom right, #B578FF, #7389FE);
}
</style>
