<template>
  <v-app>
    <v-container id="splitTitleContent">
      <v-container id="title" class="pb-0">
        <v-container class="py-0">
          <Header :cca="cca" />
        </v-container>
      </v-container>
      <v-container id="content" class="py-0">
        <v-container id="content-1">
          <AttendanceTaking
            :membersAttendance="membersAttendance"
            :attendanceWeek="attendanceWeek"
            v-on:toggle-attendance="toggleAttendance"
          />
        </v-container>
        <v-container id="content-2">
          <ViewPastAttendance :attendances="attendances" />
        </v-container>
        <v-container id="content-3">
          <TrainingTimes :trainingTimes="trainingTimes" />
        </v-container>
        <v-container id="content-4">
          <PlayersCut
            :currentPlayers="currentPlayers"
            v-on:toggle-cut="toggleCut"
            v-on:clear-cut="clearCut"
            v-on:submit-cut="submitCut"
          />
        </v-container>
        <v-container id="content-5">
          <DaysToEvent :eventDetails="eventDetails" />
        </v-container>
      </v-container>
    </v-container>
    <!-- 
        <DaysToEvent :eventDetails="eventDetails" />
        <AttendanceTaking
          :membersAttendance="membersAttendance"
          :attendanceWeek="attendanceWeek"
          v-on:toggle-attendance="toggleAttendance"
        />
        <TrainingTimes :trainingTimes="trainingTimes" />
        <PlayersCut
          :currentPlayers="currentPlayers"
          v-on:toggle-cut="toggleCut"
          v-on:clear-cut="clearCut"
          v-on:submit-cut="submitCut"
        />
        <ViewPastAttendance :attendances="attendances" />

     -->
  </v-app>
</template>

<script lang="ts">
import Vue from "vue";
import Header from "../components/Header.vue";
import DaysToEvent from "../components/DaysToEvent.vue";
import AttendanceTaking from "../components/AttendanceTaking.vue";
import TrainingTimes from "../components/TrainingTimes.vue";
import PlayersCut from "../components/PlayersCut.vue";
import ViewPastAttendance from "../components/ViewPastAttendance.vue";

export default Vue.extend({
  components: {
    Header,
    DaysToEvent,
    AttendanceTaking,
    TrainingTimes,
    PlayersCut,
    ViewPastAttendance,
  },
  data: () => {
    return {
      navItems: ["Volleyball ExCo", "My CCAs"],
      hallName: "Eusoff Hall",
      user: {
        name: "Yeoh Yong Jie",
        roomNumber: "A114",
      },
      cca: "Volleyball",
      eventDetails: {
        eventName: "IHG",
        daysToEvent: 6,
      },
      membersAttendance: [
        { name: "Yeoh Yong Jie", attended: false },
        { name: "Tom Holland", attended: true },
        { name: "Toby Maguire", attended: true },
        { name: "Andrew Garfield", attended: true },
        { name: "Wait what?", attended: false },
      ],
      attendanceWeek: {
        sem: 1,
        week: 5,
      },
      trainingTimes: [
        { day: "Tuesday", startTime: "5pm", endTime: "7pm" },
        { day: "Wednesday", startTime: "9pm", endTime: "11pm" },
      ],
      currentPlayers: [
        { name: "Yeoh Yong Jie", cut: false },
        { name: "John Doe", cut: true },
        { name: "Yuvaraj Kumaresan", cut: false },
      ],
      attendances: [
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
          name: "John Mangoseed",
          Week1Attendance: "1",
          Week2Attendance: "1",
          Week3Attendance: "0",
          Week4Attendance: "1",
        },
      ],
    };
  },
  methods: {
    toggleAttendance: function (payload: number) {
      this.membersAttendance[payload].attended =
        !this.membersAttendance[payload].attended;
    },
    toggleCut: function (payload: number) {
      this.currentPlayers[payload].cut = !this.currentPlayers[payload].cut;
    },
    clearCut: function () {
      for (var index in this.currentPlayers) {
        this.currentPlayers[index].cut = false;
      }
    },
    submitCut: function () {
      this.currentPlayers = this.currentPlayers.filter(
        (currentPlayer) => !currentPlayer.cut
      );
    },
  },
});
</script>

<style scoped>
#splitTitleContent {
  display: grid;
  grid-template-rows: auto auto auto auto auto auto auto auto auto auto;
}
#title {
  grid-row: 1 / 2;
}
#content {
  grid-row: 2 / 11;
  display: grid;
  grid-template-columns: auto auto auto;
  grid-template-rows: auto auto auto auto auto auto auto auto auto auto auto auto;
}
#content-1 {
  grid-column: 1 / 2;
  grid-row: 1 / 10;
}
#content-2 {
  grid-column: 2 / 4;
  grid-row: 1 / 9;
}
#content-3 {
  grid-column: 1 / 2;
  grid-row: 10 / 13;
}
#content-4 {
  grid-column: 2 / 3;
  grid-row: 9 / 13;
}
#content-5 {
  grid-column: 3 / 4;
  grid-row: 9 / 13;
}
</style>
