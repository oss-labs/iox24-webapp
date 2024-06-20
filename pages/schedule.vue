<template>
  <v-main class="pa-0">
    <v-container fluid>
      <v-row justify="start" align="start">
        <v-col md="9" sm="9" cols="12" class="order-md-1 order-sm-1 order-2">
          <h2 class="text-h3">Schedule</h2>
          <p>Learn about the Experts presenting at Google I/O Extended.</p>
          <br />
          <v-container fluid class="mt-3">
            <v-row v-for="(item, index) in schData" :key="index" style="border-bottom: 1px solid black;">
                <v-col md="3" cols="4">
                    <p style="text-align: end;"><b>{{ item.time }}</b></p>
                    <p style="text-align: end;">{{ item.timezone }}</p>
                </v-col>
                <v-col md="9" cols="8">
                    <p style="font-size: 120%;"><b>{{ item.title }}</b></p>
                    <p style="font-size: 90%;">{{ item.desc }}</p>
                </v-col>
              <!-- {{ item }} -->
            </v-row>
          </v-container>
        </v-col>
        <v-col md="3" sm="3" cols="12" class="order-md-2 order-sm-2 order-1 ">
          <v-img
            src="/assets/img/core/schedule.svg"
            lazy-src="/assets/img/core/schedule.svg"
          ></v-img>
        </v-col>
      </v-row>
    </v-container>
  </v-main>
</template>
    
  <script setup>
import scheduleData from "../assets/data/schedule.json";
const schData = ref([]);
schData.value = scheduleData;
</script>
    
    <style>
</style>