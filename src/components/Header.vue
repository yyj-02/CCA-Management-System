<template>
  <div class="text-h3">
    {{ cca }}
  </div>
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
