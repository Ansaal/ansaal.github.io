<template>
  <v-app>
    <v-navigation-drawer v-if="$vuetify.breakpoint.mdAndUp" value="true" app fixed color="primary">

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
        <v-icon class="mr-4">mdi-map-marker</v-icon>
        <span>Hanover, 30982 Germany</span>
      </v-row>
      <v-row class="mt-12 mb-6">
        <v-icon class="mr-4">mdi-email</v-icon>
        <a href="mailto:jhulsch.jh@gmail.com">jhulsch.jh@gmail.com</a>
      </v-row>
      <v-divider/>
      <v-row class="mt-6 mb-6">
        <span>Innovative Software Engineer with expertise in Front-End and Back-End Development. Offering 4 years of experience in full software development lifecycle. Quickly learn and master new technologies and working in both team and self-directed settings. Highly trained in software designing and process engineering.
Skilled in directing development with creative and performance-oriented approach. Well-organized and customer-focused with proven skills in project management and team leadership.</span>
      </v-row>
      <v-divider/>
      <v-row class="mt-6">
        <v-icon class="mr-4">mdi-wrench</v-icon>
        <span class="text-h5">Skills</span>
      </v-row>
      <v-list color="mb-6">
        <v-list-item class="mr-12" :key="index" v-for="(skill, index) in skills">
          <v-list-item-title>{{skill.text}}</v-list-item-title>
          <v-list-item-action>
            <v-rating
                    readonly
                    v-model="skill.value"
                    color="yellow darken-3"
                    background-color="grey darken-1"
                    empty-icon="$ratingFull"
                    half-increments
                    hover
            ></v-rating>
          </v-list-item-action>
        </v-list-item>
      </v-list>
      <v-divider/>
      <v-row class="mt-6">
        <v-icon class="mr-4">mdi-briefcase</v-icon>
        <span class="text-h5">Work history</span>
      </v-row>
      <v-row class="mt-6">
          <work-history class="mb-12" :title="work.title" :company="work.company" :texts="work.texts" :start-date="work.startDate" :end-date="work.endDate" :location="work.location" v-for="(work,index) in works" :key="index">

          </work-history>

      </v-row>
        <v-divider/>
        <v-row class="mt-6">
            <v-icon class="mr-4">mdi-school</v-icon>
            <span class="text-h5">Education</span>
        </v-row>
        <v-row class="mt-6 mb-6">
            <work-history :title="education.title" :company="education.company" :texts="education.texts" :start-date="education.startDate" :end-date="education.endDate" :location="education.location"/>
        </v-row>
        <v-divider/>
        <v-row class="mt-6">
            <v-icon class="mr-4">mdi-monitor</v-icon>
            <span class="text-h5">Sofware</span>
        </v-row>
        <v-list color="mb-6">
            <v-list-item class="mr-12" :key="index" v-for="(software, index) in softwares">
                <v-list-item-title>{{software.text}}</v-list-item-title>
                <v-list-item-action>
                    <v-rating
                            readonly
                            v-model="software.value"
                            color="yellow darken-3"
                            background-color="grey darken-1"
                            empty-icon="$ratingFull"
                            half-increments
                            hover
                    ></v-rating>
                </v-list-item-action>
            </v-list-item>
        </v-list>

        <v-divider/>
        <v-row class="mt-6">
            <v-icon class="mr-4">mdi-flag</v-icon>
            <span class="text-h5">Languages</span>
        </v-row>
        <v-list color="mb-6">
            <v-list-item class="mr-12" :key="index" v-for="(language, index) in languages">
                <v-list-item-title>{{language.text}}</v-list-item-title>
                <v-list-item-action>
                    <v-rating
                            readonly
                            v-model="language.value"
                            color="yellow darken-3"
                            background-color="grey darken-1"
                            empty-icon="$ratingFull"
                            half-increments
                            hover
                    ></v-rating>
                </v-list-item-action>
            </v-list-item>
        </v-list>

        <v-divider/>
        <v-row class="mt-6">
            <v-icon class="mr-4">mdi-flag</v-icon>
            <span class="text-h5">Hobbies</span>
        </v-row>
        <v-list color="mb-6">
            <v-list-item class="mr-12" :key="index" v-for="(language, index) in hobbies">
                <v-list-item-title>{{language}}</v-list-item-title>
            </v-list-item>
        </v-list>

    </v-main>
  </v-app>
</template>

<script lang="ts">
import Vue from "vue";
import {Component} from "vue-property-decorator";
import WorkHistory from "@/components/WorkHistory.vue";
@Component({
    components: {WorkHistory}
})
export default class App extends Vue {


  skills= [
    {text:"Software development processes", value:4},
    {text:"Proficiency with Java", value:4},
    {text:"Software development proficiency", value:4},
    {text:"Web-based software engineering", value:4},
    {text:"Agile", value:3},
    {text:"Algorithm implementation", value:4},
    {text:"Best practices", value:4},
    {text:"Programming", value:4},
    {text:"Web-Development (JavaScript/Typescript)", value:5},
  ]


    languages = [
        {text:"German", value:5},
        {text:"English", value:4},

    ]

    hobbies = [
        "Saxophone",
        "Programming",
        "Reading",
        "Cycling"
    ]

    softwares = [
        {text:"MS Office incl. Excel with VBA", value:4},
        {text:"SAP Hama & Microsoft Navision", value:3},
        {text:"IntelliJ/WebStorm/DataGrip", value:5},
        {text:"VSCode", value:4},
        {text:"Eclipse", value:4},

    ]

    works= [
        {
            title:"Software Engineer - Deployment Process",
            company: "Finanz Informatik GmbH & Co. KG",
            location: "Hanover - Germany",
            startDate: new Date(1596283200000),
            endDate: "Current",
            texts: [
                "Installed and configured software applications and tested solutions for effectiveness. Lead technical implementation of Hazelcast Memory Grid running across about 2000 Nodes on multiple data centers.",
                "Developed integrated deployment processes to help migrate from IBM WebSphere ND to WebSphere Liberty.",
                "Designed and implemented a configuration management for about 40.000 application servers in production and about 15.000 application servers in test stages.",
                "Evaluated multiple software solutions during early software architecture plotting and system migration planning stage."
            ]
        },
        {
            title:"Student Software Developer",
            company: "Finanz Informatik GmbH & Co. KG",
            location: "Hanover - Germany",
            startDate: new Date(1470052800000 ),
            endDate: new Date(1564574400000),
            texts: [
                "Implemented frontends for multiple applications focusing on AngularJS, Angular and Vue.",
                "Contributed to Java Codebase for multiple internal applications. (Logfile-Provisioning, Garbage-Collection analyzer, Configuration-Management).",
                "Student Project Manager at a project for implementing a job platform working closely together with the federal agency."
            ]
        },
        {
            title:"Apprenticeship - management assistant in IT-systems",
            company: "Anders & Rodewyk - Das Systemhaus Für Computertechnologien GmbH",
            location: "Hanover - Germany",
            startDate: new Date(1375358400000 ),
            endDate: new Date(1454241600000),
            texts: [
                "Managed customer expectations through strategic communications and helped each navigate sales processes.",
                "Helped organize sales events and meetings, including preparing materials and setting up spaces.",
                "Shadowed sales professionals to gain deeper insight into best practices and strategies for maximizing sales revenue.",
                "Tracked, measured and reported on trends for sales team analysis and decision making.",
                "Enhanced availability of infrastructure through enterprise-wide planning, thorough testing, efficient implementation and comprehensive support.",
                "Implemented corrective plans of action for network performance issues including availability, utilization, and latency."
            ]
        },
]
    education =
        {
            title:"Bachelor of Science - Business Informatics",
            company: "Hochschule Weserbergland",
            location: "Hamelin - Germany",
            startDate: new Date(1470052800000 ),
            endDate: new Date(1564574400000),
            texts: [
               "Thesis: \"Automated heuristic pattern recognition to support quality assurance in configuration management of web application server configurations from Finanz Informatik GmbH & Co. KG.\"",
                "Graduated with 2,3 GPA",
                "Majored in Informatics",
                "Minored in Business"
            ]
        };







}
</script>
