<template>
  <div>
    <v-container fluid>
      <h1>Overview</h1>
      <v-divider></v-divider>
      <h2>1. Introduction</h2>
      <p>{{overview.introduction}}</p>
    </v-container>
  </div>
</template>

<script>
import dataJson from "@/assets/data.json";
export default {
  data() {
    return {
      overview : dataJson.overviews
    };
  },
};
</script>