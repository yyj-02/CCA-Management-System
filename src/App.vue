<template>
  <v-app>
    <!-- <v-navigation-drawer absolute permanent left>
      <v-list>
        <v-list-item-content class="d-flex justify-center">
          <v-card
            class="rounded-lg primary mx-2"
            elevation="2"
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
      <v-list nav dense>
        <v-list-item-group v-model="selectedItem" color="primary">
          <v-list-item v-for="(navItem, i) in navItems" :key="i">
            <v-list-item-content>
              <v-list-item-title v-text="navItem"></v-list-item-title>
            </v-list-item-content>
          </v-list-item>
        </v-list-item-group>
      </v-list>
    </v-navigation-drawer> -->
    <!--     <v-main>
      <router-view />
    </v-main> -->
    
    <Header />
  </v-app>
</template>

<script lang="ts">
import Vue from "vue";
import Header from "./components/Header.vue";

export default Vue.extend({
  components: {
    Header,
  },
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
    };
  },
  methods: {
    toggleAttendance: function (payload: number) {
      this.membersAttendance[payload].attended =
        !this.membersAttendance[payload].attended;
    },
  },
});
</script>
