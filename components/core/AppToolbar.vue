<template>
  <v-app-bar app :elevation="0" flat color="" class="px-md-4 px-4">
    <NuxtLink to="/" style="text-decoration: none; color: black">
      <div>
        <v-img src="/assets/img//core//logo.svg" width="200"></v-img>
      </div>
    </NuxtLink>
    <!-- <v-app-bar-title to="/">
      <v-img src="/assets/img//core//logo.svg" width="200"></v-img>
    </v-app-bar-title> -->
    <div class="mx-4 d-none d-sm-none d-md-flex d-lg-flex">
      <v-btn
        variant="text"
        @click="appLoading = true"
        class="mr-1"
        to="/speakers"
        size="small"
        rounded
        >Speakers</v-btn
      >
      <v-btn
        variant="text"
        @click="appLoading = true"
        class="mr-1"
        to="/schedule"
        size="small"
        rounded
        >Schedule</v-btn
      >
      <v-btn
        variant="text"
        @click="appLoading = true"
        class="mr-1"
        to="/badge"
        size="small"
        rounded
        >Badge</v-btn
      >
      <v-btn
        variant="text"
        @click="appLoading = true"
        class="mr-1"
        to="/team"
        size="small"
        rounded
        >Team</v-btn
      >
      <v-btn
        variant="text"
        @click="appLoading = true"
        class="mr-1"
        to="/faq"
        size="small"
        rounded
        >FAQ</v-btn
      >
    </div>
    <v-spacer></v-spacer>
    <v-btn
      rounded
      v-if="
        configData &&
        configData.eventInfo.registeration.link.length &&
        new Date(configData.eventInfo.registeration.end_date) > new Date()
      "
      :href="configData.eventInfo.registeration.link"
      class="action_btn d-md-flex d-lg-flex d-sm-flex d-none"
      :size="screenWidth < 400 ? 'x-small' : 'small'"
      >Register Now</v-btn
    >
    <v-app-bar-nav-icon
      class="d-md-none d-lg-none d-sm-flex d-flex"
      @click="drawerAction"
    ></v-app-bar-nav-icon>

    <!-- {{ screenWidth }} -->
  </v-app-bar>
</template>

<script setup>
import { useDisplay } from "vuetify";
import configData from "../assets/data/config.json";
const { width, mobile } = useDisplay();
const sidebar = useSideBar();
const screenWidth = ref(0);
const configDataSet = ref([]);
const appLoading = useAppLoading();

configDataSet.value = configData;
screenWidth.value = width;

const drawerAction = () => {
  sidebar.value = !sidebar.value;
};
</script>

<style scoped>
.action_btn {
  background: linear-gradient(90deg, #faab31, #fcc731, #faab31 80%);
  color: #000;
  box-shadow: none;
  border: 0px solid black;
}
</style>
