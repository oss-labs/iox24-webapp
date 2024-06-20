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

const teamData = ref([]);
teamData.value = teamJSONData;
</script>

<style scoped>
.content-box {
  /* background-color: #eeeeee;
  border: 1.8px solid black;
  border-radius: 1rem;
  z-index: 0;
  display: flex;
  justify-content: center;
  align-items: center; */
}
.cards {
  /* display: flex;
  align-items: center;
  justify-content: space-evenly;
  padding: 2px;
  margin-top: 4rem; */
}
</style>
