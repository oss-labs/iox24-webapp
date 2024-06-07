<template>
  <v-main class="pa-0">
    <v-container fluid>
      <v-row class="d-flex">
        <v-col
          md="7"
          cols="12"
          sm="7"
          class="order-md-1 order-sm-1 order-2 py-15"
        >
          <h3 class="text-h3 font-weight-medium">Google IO Extended</h3>
          <p class="mb-4 mt-2">
            Google I/O Extended brings the excitement of Google I/O directly to
            your community.
          </p>

          <p>
            <span class="mr-4"
              ><v-icon>mdi-calendar-month</v-icon> July 23, 2024</span
            >
            <span><v-icon>mdi-map-legend</v-icon> Location</span>
          </p>

          <v-btn
            class="mt-4 mb-5"
            rounded
            variant="flat"
            color="primary"
            prepend-icon="mdi-open-in-new"
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
        <v-col md="4" cols="12">
          <h1 class="text-h4 mb-3" style="line-height: 35px">
            Occuring in the <br />
            near future
          </h1>
          <p style="font-size: 90%;">
            Google I/O Extended brings the excitement of Google I/O directly to
            your community. Join local I/O watch parties and meetups for the
            latest developer updates, technical talks from experts, networking,
            and hands-on learning.
          </p>
        </v-col>
        <v-col md="8" cols="12">
          <v-container fluid class="pa-0">
            <v-row>
              <v-col
                md="3"
                lg="3"
                sm="2"
                cols="6"
                v-for="(item, index) in stats"
                :key="index"
              >
                <v-img src="/assets/img/core/stats/stat-1.png" width="90%" class="d-flex">
                  <div
                    class="mt-5 mt-md-12 mx-md-4 mx-1 text-center align-center"
                  >
                    <!-- {{ screenWidth }} <br />
                    {{ screenWidth > 450 ? '300%' : '30px' }} -->
                    <p
                      :style="{ fontSize: screenWidth > 450 ? '350%' : '200%' }"
                    >
                      {{ item.value }}
                    </p>
                    <p style="font-size: 90%">{{ item.name }}</p>
                  </div>
                </v-img>
                <!-- <div
                  style="background-color: white; border-radius: 20px"
                  class="pa-4"
                >
                  <h2>{{ item.value }}</h2>
                  <p style="font-size: 85%">{{ item.name }}</p>
                </div> -->
              </v-col>
            </v-row>
          </v-container>
        </v-col>
      </v-row>

      <v-row class="my-15 py-10 px-1">
        <v-col md="12">
          <h1 class="mb-5">What to Expect</h1>
          <v-container fluid class="pa-0">
            <v-row>
              <v-col
                md="4"
                sm="4"
                cols="12"
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
          <h3 class="text-h3">Frequently asked questions</h3>
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
              :style="{ borderBottom: index != 3 ? '1px solid black' : '' }"
            >
              <v-expansion-panel-title
                expand-icon="mdi-menu-down"
                style="background-color: #eeeeee"
              >
                {{ item.question }}
              </v-expansion-panel-title>
              <v-expansion-panel-text
                >{{item.answer}}</v-expansion-panel-text
              >
            </v-expansion-panel>
          </v-expansion-panels>
        </v-col>
      </v-row>

      <v-row
        class="mt-10 mx-1 mb-10"
        style="
          border: 1.5px solid black;
          border-radius: 20px;
          background-color: #eeeeee;
          overflow: hidden;
        "
      >
        <v-col class="pa-0" style="border-radius: 20px">
          <div class="mx-10 mt-15" style="position: absolute">
            <h2 class="text-h3">See you at #IOExtended</h2>
            <p>
              Lorem ipsum dolor sit amet consectetur, adipisicing elit. Vitae
              laudantium reprehenderit nobis fugiat
            </p>
          </div>

          <v-img
            class="mt-10"
            src="https://io.google/2024/app/images/io24-see-you-next-year.svg"
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

faqDataSet.value = faqData
configDataSet.value = configData
screenWidth.value = width;

stats = [
  {
    name: "Speakers",
    value: "23+",
  },
  {
    name: "Participants",
    value: "200+",
  },
  {
    name: "Sessions",
    value: "10+",
  },
  {
    name: "Workshops",
    value: "2+",
  },
];

whatToExpect = [
  {
    title: "Explore",
    description:
      "Join technical sessions and Q&As to help you apply the latest announcements from Google I/O.",
    img: "https://services.google.com/fh/files/events/ioconnectexplore.png",
  },
  {
    title: "Learn",
    description:
      "Get hands-on with instructor-led workshops and check out the latest demos.  ",
    img: "https://services.google.com/fh/files/events/ioconnectlearn.png",
  },
  {
    title: "Connect",
    description:
      "Sign up to office hours and network with the people who build the technology you love. You can also expand your network and meet with other developers from India.",
    img: "https://services.google.com/fh/files/events/ioconnectconnect.png",
  },
];
</script>

<style>
</style>