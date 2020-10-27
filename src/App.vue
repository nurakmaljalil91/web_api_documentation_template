<template>
  <v-app>
    <v-navigation-drawer v-model="drawer" app>
      <v-list-item color="primary">
        <v-list-item-content>
          <v-list-item-title class="title">News Web API </v-list-item-title>
          <v-list-item-subtitle> WEB API </v-list-item-subtitle>
        </v-list-item-content>
      </v-list-item>

      <v-divider></v-divider>

      <v-list v-if="tab == 2" dense nav color="grey lighten-1">
        <v-list-item v-for="(r, index) in references" :key="index" link>
          <v-list-item-content>
            <v-list-item-title
              ><div>{{ r.title }}</div>
            </v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>

    <v-app-bar app color="primary" dark>
      <v-app-bar-nav-icon @click.stop="drawer = !drawer"></v-app-bar-nav-icon>
      <template v-slot:extension>
        <v-tabs v-model="tab">
          <v-tab>Overview</v-tab>
          <v-tab>Guide</v-tab>
          <v-tab>Reference </v-tab>
        </v-tabs></template
      ></v-app-bar
    >

    <v-main>
      <v-tabs-items v-model="tab">
        <v-tab-item :key="1"><Overview /></v-tab-item>
        <v-tab-item :key="2"><Guide /></v-tab-item>
        <v-tab-item :key="3"
          ><v-row>
            <v-col lg="8" sm="12"><SummarySection /></v-col>

            <v-col lg="4" sm="12"><ExampleSection /></v-col> </v-row
        ></v-tab-item>
      </v-tabs-items>
    </v-main>

    <v-footer
      
      class="font-weight-medium"
      color="primary"
      dark
    >
      <v-col
        class="text-center"
        cols="12"
      >
        {{ new Date().getFullYear() }} — <strong>Nur Akmal Jalil</strong>
      </v-col>
    </v-footer>
  </v-app>
</template>

<script>
import ExampleSection from "@/components/ExampleSection";
import SummarySection from "@/components/SummarySection";
import Overview from "@/components/Overview";
import Guide from "@/components/Guide";
import jsonData from "@/assets/data.json";
export default {
  name: "App",
  components: {
    Overview,
    Guide,
    ExampleSection,
    SummarySection,
  },
  data() {
    return {
      tab: null,
      drawer: null,
      references: jsonData.reference,
      
      items: [
        { title: "Overview" },
        { title: "api/BursaNews" },
        { title: "api/BursaNews/{newsid}" },
        { title: "About" },
      ],
      right: null,
    };
  },
};
</script>
