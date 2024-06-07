<template>
  <v-main class="pa-0">
    <v-container fluid>
      <v-row justify="start" align="start">
        <v-col md="7" cols="12">
          <h2 class="text-h4">Meet the Speakers</h2>
          <p>Learn about the Experts presenting at Google I/O Extended.</p>
        </v-col>
        <v-col md="5" cols="12">
          <v-img
            src="/assets/img/core/speaker-page.png"
            lazy-src="/assets/img/core/speaker-page.png"
          ></v-img>
        </v-col>
      </v-row>

      <v-row>
        <v-col md="2" v-for="(item, index) in speakersData" :key="index">
            <CommonSpeakerCard :data="item"/>
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