<template>
  <v-main class="pa-0">
    <v-container fluid>
      <v-row justify="start" align="start">
        <v-col md="12" cols="12">
          <h2 class="text-h4">Meet the Team</h2>
          <p>Learn about the Experts presenting at Google I/O Extended.</p>
        </v-col>
      </v-row>

      <v-container class="content-box pa-0 my-10 ml-0">
        <v-row>
          <v-col md="8" sm="12" cols="12" class="cards">
            <div
              v-for="(item, index) in speakersData"
              :key="index"
              class="card-items"
            >
              <CommonSpeakerCard :data="item" />
            </div>
          </v-col>
          <v-col md="4" cols="12"
            ><v-img
              src="/assets/img/core/team-IO.svg"
              lazy-src="/assets/img/core/team-IO.svg"
              max-height="380"
              max-width="100%"
            ></v-img
          ></v-col>
        </v-row>
      </v-container>
    </v-container>
  </v-main>
</template>

<script setup>
import speakersData from "../assets/data/speakers.json";

const spData = ref([]);
spData.value = speakersData;
</script>

<style scoped>
.content-box {
  background-color: #eeeeee;
  border: 1.8px solid black;
  border-radius: 1rem;
  z-index: 0;
  display: flex;
  justify-content: center;
  align-items: center;
}
.cards {
  display: flex;
  align-items: center;
  justify-content: space-evenly;
  padding: 2px;
  margin-top: 4rem;
}
</style>
