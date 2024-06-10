<template>
  <v-app-bar app :elevation="0" flat color="" class="px-4">
    <!-- <template v-slot:prepend>
      <v-app-bar-nav-icon></v-app-bar-nav-icon>
    </template> -->
    <NuxtLink to="/" style="text-decoration: none; color: black">
      <div>
        <v-img src="/assets/img//core//logo.svg" width="200"></v-img>
      </div>
      <!-- <p
        class="mb-0"
        style="font-size: 120%; text-decoration: none; color: black"
      >
        Google IO Extended
        <v-chip class="mt-n1" size="x-small" variant="flat">Baku</v-chip>
      </p> -->
    </NuxtLink>
    <!-- <v-app-bar-title to="/">
      <v-img src="/assets/img//core//logo.svg" width="200"></v-img>
    </v-app-bar-title> -->
    <div class="mx-4 d-none d-sm-none d-md-flex d-lg-flex">
      <v-btn variant="text" to="/speakers" size="small" rounded>Speakers</v-btn>
      <v-btn variant="text" to="/schedule" size="small" rounded>Schedule</v-btn>
      <v-btn variant="text" to="/badge" size="small" rounded>Badge</v-btn>
      <v-btn variant="text" to="/team" size="small" rounded>Team</v-btn>
      <v-btn variant="text" to="/faq" size="small" rounded>FAQ</v-btn>
    </div>
    <v-spacer></v-spacer>
    <v-btn
      rounded
      class="action_btn"
      :size="screenWidth < 400 ? 'x-small' : 'small'"
      >Register Now</v-btn
    >
    <!-- {{ screenWidth }} -->
  </v-app-bar>
</template>

<script setup>
import { useDisplay } from "vuetify";
const { width, mobile } = useDisplay();
const screenWidth = ref(0);

screenWidth.value = width;
</script>

<style scoped>
.action_btn {
  background: linear-gradient(90deg, #faab31, #fcc731, #faab31 80%);
  color: #000;
  box-shadow: none;
  border: 2px solid black;
}
</style>
