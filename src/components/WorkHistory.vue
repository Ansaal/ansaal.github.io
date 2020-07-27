<template>
  <v-card style="width: 100%" class="mr-12">
    <v-card-title>{{ title }}</v-card-title>
    <v-card-subtitle style="padding-bottom: 0px" class="px-7"
      ><v-row>{{ company }}<v-spacer />{{ location }}</v-row></v-card-subtitle
    >
    <v-card-subtitle style="padding-top: 0px;" class="px-4"
      >{{ startDateFormatted }}-{{ endDateFormatted }}</v-card-subtitle
    >
    <v-card-text>
      <v-row v-for="(text, index) in texts" :key="index">
        <li>{{ text }}</li>
      </v-row>
    </v-card-text>
  </v-card>
</template>

<script lang="ts">
import { Component, Prop, Vue } from "vue-property-decorator";

@Component
export default class WorkHistory extends Vue {
  @Prop()
  title!: string;

  @Prop()
  company!: string;

  @Prop()
  location!: string;

  @Prop()
  texts!: Array<string>;

  @Prop()
  startDate!: Date | string;

  @Prop()
  endDate!: Date | string;

  get startDateFormatted() {
    if (this.startDate instanceof Date) {
      return this.startDate.toLocaleDateString();
    }
    return this.startDate;
  }

  get endDateFormatted() {
    if (this.endDate instanceof Date) {
      return this.endDate.toLocaleDateString();
    }
    return this.endDate;
  }
}
</script>

<style scoped></style>
