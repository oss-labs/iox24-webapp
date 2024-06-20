<template>
  <v-navigation-drawer v-model="sidebar" app floating temporary location="bottom">
    <v-list-item class="py-4" title="Google IO Extended" :subtitle="configDataSet.communityName"></v-list-item>
    <v-divider></v-divider>
    <v-list-item link title="Home" to="/"></v-list-item>
    <v-list-item link title="Speakers" to="/speakers"></v-list-item>
    <v-list-item link title="Schedule" to="/schedule"></v-list-item>
    <v-list-item link title="Badge" to="/badge"></v-list-item>
    <v-list-item link title="Team" to="/team"></v-list-item>
    <v-list-item link title="FAQ" to="/faq"></v-list-item>
  </v-navigation-drawer>
</template>

<script setup>
import configData from "../assets/data/config.json";
const sidebar = useSideBar();
const configDataSet = ref([]);
configDataSet.value = configData;
</script>

<style>
</style>