<template>
  <v-app>
    <v-navigation-drawer v-model="drawer" app>
      <v-list-item color="primary">
        <v-list-item-content>
          <v-list-item-title class="title">
            BursaNews Web API
          </v-list-item-title>
          <v-list-item-subtitle> subtext </v-list-item-subtitle>
        </v-list-item-content>
      </v-list-item>

      <v-divider></v-divider>

      <v-list dense nav color="grey lighten-1" dark>
        <v-list-item v-for="item in items" :key="item.title" link>
          <v-list-item-content>
            <v-list-item-title>{{ item.title }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
    <v-app-bar app color="primary" dark>
      <v-app-bar-nav-icon @click.stop="drawer = !drawer"></v-app-bar-nav-icon
    ></v-app-bar>

    <v-main>
      <v-row>
        <v-col cols="6"><SummarySection /></v-col>

        <v-col cols="6"><ExampleSection /></v-col>
      </v-row>
    </v-main>
  </v-app>
</template>

<script>
import ExampleSection from "@/components/ExampleSection";
import SummarySection from "@/components/SummarySection";
export default {
  name: "App",
  components: {
    ExampleSection,
    SummarySection,
  },
  data() {
    return {
      drawer: null,
      items: [
        { title: "GET /api/BursaNews" },
        { title: "GET /api/BursaNews/{newsid}" },
        { title: "About" },
      ],
      right: null,
    };
  },
};
</script>
