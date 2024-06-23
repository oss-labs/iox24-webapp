<template>
  <v-container fluid class="google-font">
    <v-row class="my-0">
      <v-col md="12">
        <p
          class="google-font gdg-h1 mb-2 grey--text text--darken-4"
          style="font-size: 220%"
        >
          Our Partners
        </p>
        <p class="mb-0">
          Partners dedicated to building remarkable experience!
        </p>
      </v-col>
    </v-row>
    <partnerVue />
  </v-container>
</template>

<script>
import partnerVue from "../common/partner.vue";
export default {
  name: "PartnersComponets",
  components: {
    partnerVue,
  },
  data: () => ({}),
};
</script>

<style></style>
