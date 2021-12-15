<template>
  <v-container>
    <v-card class="rounded-xl" elevation="4" height="100%" width="100%">
      <v-card-title class="headline font-weight-medium">
        Attendance Taking
      </v-card-title>
      <v-card-subtitle>
        Sem {{ attendanceWeek.sem }} Week {{ attendanceWeek.week }}
      </v-card-subtitle>
      <v-card-text>
        <v-list>
          <v-list-item
            v-for="(member, index) in membersAttendance"
            :key="index"
          >
            <v-list-item-action>
              <v-checkbox
                color="purple"
                :input-value="member.attended"
                @click="toggleAttendance(index)"
              ></v-checkbox>
            </v-list-item-action>
            <v-list-item-content>
              <v-list-item-title>{{ member.name }}</v-list-item-title>
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
    membersAttendance: {
      default: [
        { name: "Yeoh Yong Jie", attended: true },
        { name: "Yuvaraj Kumaresan", attended: false },
      ],
    },
    attendanceWeek: {
      default: {
        sem: 1,
        week: 5,
      },
    },
  },
  methods: {
    toggleAttendance: function (index: number) {
      this.$emit("toggle-attendance", index);
    },
  },
});
</script>
