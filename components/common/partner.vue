<template>
  <v-container fluid class="pa-0">
    <v-row
      v-for="(item, index) in partnersInfo"
      :key="index"
      class="google-font mb-5 mt-0"
    >
      <v-col md="12" cols="12" class="mb-n1">
        <b>{{ item.category_name }}</b>
      </v-col>
      <v-col
        md="2"
        cols="6"
        sm="3"
        class="text-center"
        v-for="(partner, indexp) in item.partners"
        :key="indexp"
      >
        <div class="pa-5 partner-box">
          <v-tooltip bottom>
            <template v-slot:activator="{ on, attrs }">
              <a :href="partner.link" target="_blank" v-bind="attrs" v-on="on">
                <v-img :src="`/partners/${partner.logo}`" />
              </a>
            </template>
            <span>{{ partner.name }}</span>
          </v-tooltip>
        </div>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
import partnersJSON from "@/assets/data/partners.json";
export default {
  name: "PartnersData",
  data: () => ({
    partnersInfo: partnersJSON,
  }),
};
</script>

<style scoped>
.partner-box {
  border: 1px solid black;
  background-color: #eeeeee;
  border-radius: 15px;
}
</style>
