<template>
  <v-app>
    <v-navigation-drawer value="true" app permanent fixed color="primary">

    </v-navigation-drawer>
    <v-main class="ml-12">
      <v-row class="justify-start">
      <div class="display-3 text--primary" style="font-weight: bolder; color:#1a237e!important;">
        Johannes Hulsch
      </div>
      </v-row>
      <v-row>
        <div class="display-1">
          Software Engineer
        </div>
      </v-row>
      <v-row class="mt-12">
        <v-icon>mdi-map-marker</v-icon>
        <span>Hanover, 30982 Germany</span>
      </v-row>
      <v-row class="mt-12">
        <v-icon>mdi-email</v-icon>
        <a href="mailto:jhulsch.jh@gmail.com">jhulsch.jh@gmail.com</a>
      </v-row>
    </v-main>
  </v-app>
</template>

<script lang="ts">
import Vue from "vue";
import {Component} from "vue-property-decorator";

@Component
export default class App extends Vue {



}
</script>
