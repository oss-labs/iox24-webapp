<template>
  <v-main class="pa-0">
    <v-container fluid class="px-0">
      <v-row justify="start" align="start">
        <v-col md="12" cols="12">
          <h2 class="text-h3">Meet the Team</h2>
          <p>Learn about the Experts presenting at Google I/O Extended.</p>
        </v-col>
      </v-row>

      <v-row style="" class="mb-15">
        <v-col md="8" cols="12">
          <v-container fluid class="px-0">
            <v-row>
              <v-col
                md="3"
                sm="12"
                cols="6"
                class="pa-5"
                v-for="(item, index) in teamData"
                :key="index"
              >
                <CommonSpeakerCard :data="item" />
              </v-col>
            </v-row>
          </v-container>
        </v-col>
        <v-col
          md="4"
          cols="12"
          class="action_btn d-md-flex d-lg-flex d-sm-flex d-none"
        >
          <v-img
            src="/assets/img/core/team-IO.svg"
            lazy-src="/assets/img/core/team-IO.svg"
            max-height="380"
            max-width="100%"
          ></v-img>
        </v-col>
      </v-row>
    </v-container>
  </v-main>
</template>

<script setup>
import teamJSONData from "../assets/data/team.json";
import configData from "../assets/data/config.json";
const configDataSet = ref([]);
configDataSet.value = configData;

const teamData = ref([]);
teamData.value = teamJSONData;



useSeoMeta({
  contentType: "text/html; charset=utf-8",
  title: 'Team - '+configDataSet.value.eventInfo.name + ' | '+configDataSet.value.communityName,
  description: configDataSet.value.eventInfo.description.short,
  keywords: configDataSet.value.seo.keywords,
  author: "OSS Labs",
  creator: "OSS Labs",
  viewport: "width=device-width, initial-scale=1.0",
  ogTitle: 'Team - '+configDataSet.value.eventInfo.name + ' | '+configDataSet.value.communityName,
  ogDescription: configDataSet.value.eventInfo.description.short,
  ogImage: `${configDataSet.value.seo.hostUrl}/thumbnail.png?auto=format&fit=crop&frame=1&h=512&w=1024`,
  ogUrl: configDataSet.value.seo.hostUrl,
  ogType: "website",
  twitterTitle: 'Team - '+configDataSet.value.eventInfo.name + ' | '+configDataSet.value.communityName,
  twitterDescription: configDataSet.value.eventInfo.description.short,
  twitterImage: `${configDataSet.value.seo.hostUrl}thumbnail.png?auto=format&fit=crop&frame=1&h=512&w=1024`,
  twitterCard: "summary_large_image",
});
</script>

<style scoped>
</style>
