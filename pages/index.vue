<template>
  <v-main class="pa-0">
    <v-container fluid class="px-0">
      <v-row class="d-flex">
        <v-col
          md="7"
          cols="12"
          sm="7"
          class="order-md-1 order-sm-1 order-2 py-15"
        >
          <h3 class="text-h3 font-weight-medium">Google I/O Extended</h3>
          <p style="font-weight: 600">
            {{ configDataSet.communityLocation.city }}
          </p>
          <p class="mb-4 mt-2">
            {{ configDataSet.eventInfo.description.short }}
          </p>

          <p>
            <span class="mr-4"
              ><v-icon>mdi-calendar-month</v-icon>
              {{ configData.eventInfo.date }}</span
            >
            <span
              ><v-icon>mdi-map-legend</v-icon>
              <a
                style="text-decoration: none; color: #2987f6"
                :href="configDataSet.eventInfo.venue.map_link"
                >{{ configData.eventInfo.venue.address }}</a
              >
            </span>
          </p>

          <v-btn
            class="my-5 action_btn"
            v-if="
              configData.eventInfo.registeration.link.length &&
              new Date(configData.eventInfo.registeration.end_date) <<
                new Date()
            "
            size="large"
            :href="configData.eventInfo.registeration.link"
            target="_blank"
            rounded
            >Register Now</v-btn
          >
        </v-col>
        <v-col
          md="5"
          cols="12"
          sm="5"
          class="order-md-2 order-sm-2 order-1 mt-10 align-self-end pa-0"
        >
          <v-img width="200vh" src="/assets/img/core/hero.png"></v-img>
        </v-col>
      </v-row>

      <v-row
        justify="center"
        align="center"
        style="
          border: 1px solid black;
          border-radius: 20px;
          background-color: #eeeeee;
        "
        class="pa-3 mx-1"
      >
        <v-col md="5" cols="12">
          <h1 class="text-h3 mb-3" style="line-height: 45px">
            Occuring in the <br />
            near future
          </h1>
          <p style="font-size: 95%">
            {{ configDataSet.eventInfo.description.long }}
          </p>
        </v-col>
        <v-col md="7" cols="12">
          <v-container fluid class="pa-0">
            <v-row>
              <v-col
                md="3"
                lg="3"
                sm="3"
                cols="6"
                v-for="(item, index) in stats"
                :key="index"
              >
                <v-img
                  src="/assets/img/core/stats/stat-1.png"
                  width="90%"
                  class="d-flex"
                >
                  <div
                    class="mt-5 mt-md-12 mx-md-4 mx-1 text-center align-center img-content"
                  >
                    <p
                      :style="{ fontSize: screenWidth > 450 ? '350%' : '180%' }"
                    >
                      {{ item.value }}
                    </p>
                    <p style="font-size: 90%">{{ item.name }}</p>
                  </div>
                </v-img>
              </v-col>
            </v-row>
          </v-container>
        </v-col>
      </v-row>

      <v-row class="my-15 pt-10 px-1">
        <v-col md="12">
          <h1 class="mb-5 text-h4">What to Expect</h1>
          <v-container fluid class="pa-0">
            <v-row>
              <v-col
                md="4"
                sm="4"
                cols="12"
                class="mb-4"
                v-for="(item, index) in whatToExpect"
                :key="index"
              >
                <v-card flat>
                  <v-img
                    style="
                      border-radius: 20px;
                      border-radius: 20px;
                      border: 1px solid black;
                    "
                    :src="item.img"
                  ></v-img>
                  <h2 class="my-3">{{ item.title }}</h2>
                  <p>{{ item.description }}</p>
                </v-card>
              </v-col>
            </v-row>
          </v-container>
        </v-col>
      </v-row>

      <v-row class="px-1">
        <v-col md="10">
          <h3 class="text-h4">Frequently asked questions</h3>
          <p class="mb-4">Need Answers? Everything you need to know</p>
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
              :style="{ borderBottom: index+1 < faqDataSet.length ? '1px solid black' : '' }"
            >
              <v-expansion-panel-title
                expand-icon="mdi-menu-down"
                style="background-color: #eeeeee"
              >
                {{ item.question }}
              </v-expansion-panel-title>
              <v-expansion-panel-text class="pa-3">
                <div v-html="item.answer"></div>
              </v-expansion-panel-text>
            </v-expansion-panel>
          </v-expansion-panels>
        </v-col>
      </v-row>

      <v-row
        class="mt-10 mx-1 mb-10"
        style="
          border: 1px solid black;
          border-radius: 20px;
          background-color: #eeeeee;
          overflow: hidden;
        "
      >
        <v-col class="pa-0" style="border-radius: 20px">
          <div class="mx-8 mt-8 mx-md-15 mt-md-10">
            <h2 class="text-h4">See you at #IOExtended</h2>
          </div>

          <v-img
            class="mt-10"
            src="https://io.google/2024/app/images/io24-see-you-next-year.svg"
            lazy-src="https://io.google/2024/app/images/io24-see-you-next-year.svg"
          ></v-img>
        </v-col>
      </v-row>
    </v-container>
  </v-main>
</template>

<script setup>
import { useDisplay } from "vuetify";
import configData from "../assets/data/config.json";
import faqData from "../assets/data/faq.json";

const { width, mobile } = useDisplay();

const screenWidth = ref(0);
const faqDataSet = ref([]);
const configDataSet = ref([]);
let whatToExpect = ref([]);
let stats = ref([]);

faqDataSet.value = faqData;
configDataSet.value = configData;
screenWidth.value = width;

stats.value = configDataSet.value.eventInfo.stats;
whatToExpect.value = configDataSet.value.eventInfo.whatToExpect;

useSeoMeta({
  contentType: "text/html; charset=utf-8",
  title:
    configDataSet.value.eventInfo.name +
    " | " +
    configDataSet.value.communityName,
  description: configDataSet.value.eventInfo.description.short,
  keywords: configDataSet.value.seo.keywords,
  author: "OSS Labs",
  creator: "OSS Labs",
  viewport: "width=device-width, initial-scale=1.0",
  ogTitle:
    configDataSet.value.eventInfo.name +
    " | " +
    configDataSet.value.communityName,
  ogDescription: configDataSet.value.eventInfo.description.short,
  ogImage: `${configDataSet.value.seo.hostUrl}/thumbnail.png?auto=format&fit=crop&frame=1&h=512&w=1024`,
  ogUrl: configDataSet.value.seo.hostUrl,
  ogType: "website",
  twitterTitle:
    configDataSet.value.eventInfo.name +
    " | " +
    configDataSet.value.communityName,
  twitterDescription: configDataSet.value.eventInfo.description.short,
  twitterImage: `${configDataSet.value.seo.hostUrl}thumbnail.png?auto=format&fit=crop&frame=1&h=512&w=1024`,
  twitterCard: "summary_large_image",
});
</script>

<style scoped>
.action_btn {
  background: linear-gradient(90deg, #4285f4, #a16bcc, #ea4335 80%);
  color: white;
  /* color: #000; */
  box-shadow: none;
  border: 0px solid black;
}
@media screen and (max-width: 1440px) {
  .mt-md-12 {
    margin-top: 0px !important;
  }
  .img-content p:first-child {
    margin-top: 1rem;
  }
}
@media screen and (max-width: 1080px) {
  .mx-md-4 {
    margin-right: 0px !important;
    margin-left: 0px !important;
  }
}
</style>
