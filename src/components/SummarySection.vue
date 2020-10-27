<template>
  <div>
    <v-container fluid>
      <h1>Bursanews Web API</h1>
      <v-divider></v-divider>
      <strong >
        Endpoints for retrieving information news
        habits.</strong
      >
      <p>Base URL: {{info.baseUrl}}</p>
      <v-expansion-panels>
        <v-expansion-panel v-for="(r, index) in references" :key="index">
          <v-expansion-panel-header>
            <v-row>
              <v-col cols="4"
                ><strong>{{ r.title }} </strong></v-col
              >
              <v-col cols="4"
                ><div class="green--text">
                  <strong> {{ r.method }}</strong>
                </div></v-col
              >
              <v-col cols="4">
                <div class="orange--text">{{ r.url }}</div>
              </v-col>
            </v-row>
          </v-expansion-panel-header>
          <v-expansion-panel-content>
            <v-row>
              <v-col cols="3">Description:</v-col>
              <v-col cols="9">{{ r.description }}</v-col>
              <v-col cols="12">URL Paramaters:</v-col>
              <v-col cols="12">
                <v-container fluid class="grey lighten-3"
                  ><code>
                    {{ r.urlParams }}
                  </code></v-container
                >
              </v-col>

              <v-col cols="12">Data Parameters:</v-col>
              <v-col cols="12">
                <v-container fluid class="grey lighten-3"
                  ><code>
                    {{ r.urlParams }}
                  </code></v-container
                >
              </v-col>
              <v-col cols="12">Success Response:</v-col>
              <v-col cols="12">Code:</v-col>
              <v-col cols="12">
                <v-container fluid class="deep-orange lighten-5"
                  ><code>
                    {{ r.successResponse[0].code }}
                  </code></v-container
                >
              </v-col>
              <v-col cols="12">Content:</v-col>
              <v-col cols="12">
                <v-container fluid class="grey lighten-3"
                  ><div v-html="r.successResponse[0].content"></div
                ></v-container>
              </v-col>
              <v-col cols="12">Sample Call:</v-col>
              <v-col cols="12">
                <v-container fluid class="grey lighten-3"
                  ><code class="grey lighten-3 black--text">
                    {{ r.sampleCall }}
                  </code></v-container
                >
              </v-col>
            </v-row>
          </v-expansion-panel-content>
        </v-expansion-panel>
      </v-expansion-panels>
    </v-container>
  </div>
</template>

<script>
import dataJson from "@/assets/data.json";
export default {
  data() {
    return {
      references: dataJson.reference,
      info: dataJson.info,
    };
  },
};
</script>