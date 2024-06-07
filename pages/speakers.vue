<template>
  <v-main class="">
    <v-container fluid>
      <v-row justify="center" align="center">
        <v-col md="8">
          <h2 class="text-h2">Meet the Speakers</h2>
          <p>Learn about the Experts presenting at Google I/O Extended.</p>
        </v-col>
        <v-col md="4">
          <!-- <v-img
            src="/assets/img/core/"
          ></v-img> -->
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