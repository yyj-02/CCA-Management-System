<template>
  <v-container>
    <v-card class="rounded-xl" elevation="2" height="100%" width="100%">
      <v-card-title class="headline font-weight-medium">
        View Past Attendance
      </v-card-title>
      <v-simple-table>
        <template v-slot:default>
          <thead>
            <tr>
              <th class="text-left">Name</th>
              <th class="text-left">Week 1</th>
              <th class="text-left">Week 2</th>
              <th class="text-left">Week 3</th>
              <th class="text-left">Week 4</th>
            </tr>
          </thead>
          <tbody>
            <tr v-for="(attendance, index) in attendances" :key="index">
              <td>{{ attendance.name }}</td>
              <td>{{ attendance.Week1Attendance }}</td>
              <td>{{ attendance.Week2Attendance }}</td>
              <td>{{ attendance.Week3Attendance }}</td>
              <td>{{ attendance.Week4Attendance }}</td>
            </tr>
          </tbody>
        </template>
      </v-simple-table>
    </v-card>
  </v-container>
</template>
<script lang="ts">
import Vue from "vue";
export default Vue.extend({
  props: {
    attendances: {
      default: [
        {
          name: "Yuvaraj",
          Week1Attendance: "0",
          Week2Attendance: "1",
          Week3Attendance: "0",
          Week4Attendance: "1",
        },
        {
          name: "Yong Jie",
          Week1Attendance: "1",
          Week2Attendance: "0",
          Week3Attendance: "1",
          Week4Attendance: "1",
        },
        {
          name: "John Doe",
          Week1Attendance: "0",
          Week2Attendance: "0",
          Week3Attendance: "1",
          Week4Attendance: "0",
        },
        {
          name: "John Appleseed",
          Week1Attendance: "1",
          Week2Attendance: "1",
          Week3Attendance: "0",
          Week4Attendance: "1",
        },
      ],
    },
  },
});
</script>
