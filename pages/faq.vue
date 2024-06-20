<template>
  <v-main class=" pa-0 ma-0">
    <v-container fluid class="">
      <v-row justify="" align="start">
        <v-col md="9" sm="9" cols="12" class="order-md-1 order-sm-1 order-2">
          <h2 class="text-h3">Frequently asked questions</h2>
          <p class="mb-10">Need Answers? Everything you need to know</p>

          <v-expansion-panels
            class="mb-6"
            rounded="12"
            bg-color="white"
            flat
            style="
              border-radius: 20px !important;
              /* border-bottom: 1px solid black; */
              overflow: hidden;
            "
            variant="accordion"
          >
            <!-- :style="{ borderBottom: i<3?'1px solid black':'', borderTop: i!=0?'1px solid black':'' }" -->
            <v-expansion-panel
              v-for="(item, index) in faqDataSet"
              :key="index"
              :style="{ borderBottom: index != 3 ? '1px solid black' : '' }"
            >
              <v-expansion-panel-title
                expand-icon="mdi-menu-down"
                style="background-color: #eeeeee"
              >
                {{ item.question }}
              </v-expansion-panel-title>
              <v-expansion-panel-text>{{ item.answer }}</v-expansion-panel-text>
            </v-expansion-panel>
          </v-expansion-panels>
        </v-col>
      </v-row>
    </v-container>
  </v-main>
</template>

<script setup>
import faqData from "../assets/data/faq.json";
const faqDataSet = ref([]);
faqDataSet.value = faqData;
</script>

<style></style>
