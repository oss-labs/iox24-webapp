<template>
  <v-main class="pa-0">
    <v-container fluid class="">
      <v-row
        justify="center"
        align="center"
        class="px-md-10"
        style="
          border: 1px solid black;
          border-radius: 20px;
          background-color: #eeeeee;
        "
      >
        <v-col md="7" sm="7" cols="12">
          <h2 class="text-h3">Meet the Speakers</h2>
          <p>Learn about the Experts presenting at Google I/O Extended.</p>
        </v-col>
        <v-col md="5" sm="5" cols="12" class="mb-2">
          <v-img
            src="/assets/img/core/speaker-page.png"
            lazy-src="/assets/img/core/speaker-page.png"
          ></v-img>
        </v-col>
      </v-row>

      <v-row class="px-0 my-10">
        <v-col
          md="2"
          lg="2"
          sm="3"
          cols="6"
          v-for="(item, index) in speakersData"
          :key="index"
        >
          <!-- {{ item }} -->
          <CommonSpeakerCard :data="item" />
        </v-col>
      </v-row>
    </v-container>
  </v-main>
</template>

<script setup>
import speakersData from "../assets/data/speakers.json";
import configData from "../assets/data/config.json";
const configDataSet = ref([]);
configDataSet.value = configData;

const spData = ref([]);
spData.value = speakersData;
useSeoMeta({
  contentType: "text/html; charset=utf-8",
  title:
    "Speakers - " +
    configDataSet.value.eventInfo.name +
    " | " +
    configDataSet.value.communityName,
  description: configDataSet.value.eventInfo.description.short,
  keywords: configDataSet.value.seo.keywords,
  author: "OSS Labs",
  creator: "OSS Labs",
  viewport: "width=device-width, initial-scale=1.0",
  ogTitle:
    "Speakers - " +
    configDataSet.value.eventInfo.name +
    " | " +
    configDataSet.value.communityName,
  ogDescription: configDataSet.value.eventInfo.description.short,
  ogImage: `${configDataSet.value.seo.hostUrl}/thumbnail.png?auto=format&fit=crop&frame=1&h=512&w=1024`,
  ogUrl: configDataSet.value.seo.hostUrl,
  ogType: "website",
  twitterTitle:
    "Speakers - " +
    configDataSet.value.eventInfo.name +
    " | " +
    configDataSet.value.communityName,
  twitterDescription: configDataSet.value.eventInfo.description.short,
  twitterImage: `${configDataSet.value.seo.hostUrl}thumbnail.png?auto=format&fit=crop&frame=1&h=512&w=1024`,
  twitterCard: "summary_large_image",
});
</script>

<style>
</style>
