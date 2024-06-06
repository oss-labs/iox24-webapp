<template>
  <v-app-bar
    :elevation="0"
    flat
    class="px-4"
    style="border-bottom: 1.5px solid black"
  >
    <!-- <template v-slot:prepend>
      <v-app-bar-nav-icon></v-app-bar-nav-icon>
    </template> -->
    <NuxtLink to="/" style="text-decoration: none;color: black;">
      <p class="mb-0" style="font-size: 120%;text-decoration: none;color: black;">
      Google IO Extended
      <v-chip class="mt-n1" size="x-small" variant="flat">Baku</v-chip>
    </p>
    </NuxtLink>
    <!-- <v-app-bar-title to="/">Google IO Extended</v-app-bar-title> -->
    <div class="mx-4 d-none d-sm-none d-md-flex d-lg-flex">
      <v-btn variant="text" to="/speakers" size="small" rounded>Speakers</v-btn>
      <v-btn variant="text" to="/schedule" size="small" rounded>Schedule</v-btn>
      <v-btn variant="text" to="/badge" size="small" rounded>Badge</v-btn>
      <v-btn variant="text" to="/team" size="small" rounded>Team</v-btn>
      <v-btn variant="text" to="/faq" size="small" rounded>FAQ</v-btn>
    </div>
    <v-spacer></v-spacer>
    <v-btn rounded :size="screenWidth<400?'x-small':'small'" variant="flat" color="primary" prepend-icon="mdi-open-in-new"
      >Register Now</v-btn
    >
    <!-- {{ screenWidth }} -->
  </v-app-bar>
</template>

<script setup>
import { useDisplay } from 'vuetify'
const { width, mobile } = useDisplay()
const screenWidth = ref(0)

screenWidth.value = width

</script>

<style>
</style>