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
        <v-col md="7" cols="12">
          <h2 class="text-h3">Meet the Speakers</h2>
          <p>Learn about the Experts presenting at Google I/O Extended.</p>
        </v-col>
        <v-col md="5" cols="12" class="mb-2">
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
const spData = ref([]);
spData.value = speakersData;
</script>

<style>
</style>
