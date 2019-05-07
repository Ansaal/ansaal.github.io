<template>
  <v-app dark>
    <v-navigation-drawer v-model="drawer" clipped app>
      <v-list dense>
        <v-list-tile v-for="item in navigation.routes" :key="item.text" @click :to="item.path">
          <v-list-tile-action>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-tile-action>
          <v-list-tile-content>
            <v-list-tile-title>{{ item.text }}</v-list-tile-title>
          </v-list-tile-content>
        </v-list-tile>
        <v-divider/>
        <v-list-tile class="mt-3" @click>
          <v-list-tile-action>
            <v-icon>add_circle_outline</v-icon>
          </v-list-tile-action>
          <v-list-tile-title>Browse Repositories</v-list-tile-title>
        </v-list-tile>
        <v-list-tile @click to="/contact">
          <v-list-tile-action>
            <v-icon>perm_contact_calendar</v-icon>
          </v-list-tile-action>
          <v-list-tile-title>Contact</v-list-tile-title>
        </v-list-tile>
      </v-list>
    </v-navigation-drawer>
    <v-toolbar fixed clipped-left app>
      <v-toolbar-side-icon @click.stop="drawer=!drawer"></v-toolbar-side-icon>
      <v-toolbar-title class="headline text-uppercase">
        <span>ANSAAL</span>
        <span class="ml-2 font-weight-light">Fullstack-DEVELOPMENT</span>
      </v-toolbar-title>
    </v-toolbar>

    <v-content>
      <router-view></router-view>
    </v-content>
  </v-app>
</template>

<script lang="ts">
import Vue from "vue";
import Component from "vue-class-component";
@Component({
  components: {}
})
export default class App extends Vue {
  name: string = "App";
  drawer: boolean = false;



  navigation = {
    routes: [
      { text: "Home", icon: "home", path: "/" },
      { text: "Web-Development", icon: "web", path: "/web" },
      { text: "Machine-Learning", icon: "show_chart", path: "/ml" },

    ]
  }

}
</script>
