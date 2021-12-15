<template>
  <v-app>
    <v-navigation-drawer v-mode="null" absolute permanent left>
      <v-list>
        <v-list-item-content class="d-flex justify-center">
          <v-card
            id="grad"
            class="rounded-xl primary mx-2"
            elevation="4"
            max-width="90%"
            tile
          >
            <v-card-title class="white--text">{{ hallName }}</v-card-title>
            <v-card-subtitle class="white--text">
              {{ user.name }} - {{ user.roomNumber }}
            </v-card-subtitle>
          </v-card>
        </v-list-item-content>
      </v-list>
      <v-list nav rounded>
        <v-list-item-group v-model="selectedItem" color="deep-purple">
          <v-list-item v-for="(navItem, i) in navItems" :key="i">
            <v-list-item-content>
              <v-list-item-title v-text="navItem"></v-list-item-title>
            </v-list-item-content>
          </v-list-item>
        </v-list-item-group>
      </v-list>
    </v-navigation-drawer>
    <v-main id="main">
      <router-view />
    </v-main>
  </v-app>
</template>

<script lang="ts">
import Vue from "vue";
export default Vue.extend({
  data: () => {
    return {
      navItems: ["Volleyball ExCo", "My CCAs"],
      hallName: "Eusoff Hall",
      user: {
        name: "Yeoh Yong Jie",
        roomNumber: "A114",
      },
      membersAttendance: [
        { name: "Yeoh Yong Jie", attended: true },
        { name: "Yuvaraj Kumaresan", attended: false },
        { name: "Encik Jackie", attended: false },
      ],
      attendanceWeek: {
        sem: 1,
        week: 5,
      },
      currentPlayers: [
        { name: "Yeoh Yong Jie", cut: false },
        { name: "John Doe", cut: true },
        { name: "Yuvaraj Kumaresan", cut: false },
      ],
    };
  },
});
</script>

<style scoped>
#grad {
  background-image: linear-gradient(to bottom right, #b578ff, #7389fe);
}
#main {
  width: calc(100% - 256px);
  position: relative;
  left: 256px;
}
</style>
