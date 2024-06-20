<template>
  <NuxtLayout>
    <v-app>
      <CoreAppToolbar />
      <CoreAppDrawer />
      <v-main class="pa-0">
        <CoreAppBanner
          v-if="
            configData.eventInfo.registeration.link.length &&
            new Date(configData.eventInfo.registeration.end_date) << new Date()
          "
        />
        <v-container fluid>
          <v-row justify="center" align="start">
            <v-col md="11" lg="10">
              <NuxtPage />
            </v-col>
          </v-row>
        </v-container>
      </v-main>
      <CoreAppFooter />
    </v-app>
  </NuxtLayout>
</template>

<script setup>
import configData from "../assets/data/config.json";
const configDataSet = ref([]);
configDataSet.value = configData;
</script>
