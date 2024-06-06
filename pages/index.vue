<template>
  <v-main>
    <v-container fluid>
      <v-row justify="center" align="center" class="mb-15">
        <v-col md="8" cols="12" sm="7" class="order-md-1 order-sm-1 order-2">
          <h1 class="text-h2">Google IO Extended</h1>
          <p class="my-4">
            Google I/O Extended brings the excitement of Google I/O directly to
            your community. Join local I/O watch parties and meetups for the
            latest developer updates, technical talks from experts, networking,
            and hands-on learning.
          </p>

          <p><v-icon>mdi-calendar-month</v-icon> July 23, 2024</p>
          <p><v-icon>mdi-map-legend</v-icon> Location</p>
          <v-btn
            class="mt-4"
            rounded
            variant="flat"
            color="primary"
            prepend-icon="mdi-open-in-new"
            >Register Now</v-btn
          >
        </v-col>
        <v-col md="4" cols="12" sm="5" class="order-md-2 order-sm-2 order-1">
          <v-img
            src="https://io.google/2024/app/images/io24-home-hero-phase4-2.svg"
          ></v-img>
        </v-col>
      </v-row>

      <v-row
        justify="center"
        align="center"
        style="
          border: 1.5px solid black;
          border-radius: 20px;
          background-color: #eeeeee;
        "
        class="pa-3 mx-1 my-10"
      >
        <v-col>
          <h1>Occuring in the near future</h1>
          <p>
            Whether it be through technical talks delivered in local languages,
            Q&As with local Google Developer Experts, or by simply meeting
            fellow local tech enthusiasts, I/O Extended attendees learn about
            how Google developer products can help them do what they do best -
            develop.
          </p>

          <v-container fluid class="pa-0 mt-5">
            <v-row>
              <v-col md="2" lg="2" sm="2" cols="6" v-for="(item, index) in stats" :key="index">
                <div
                  style="background-color: white; border-radius: 20px"
                  class="pa-4"
                >
                  <h2>{{ item.value }}</h2>
                  <p style="font-size: 85%">{{ item.name }}</p>
                </div>
              </v-col>
            </v-row>
          </v-container>
        </v-col>
      </v-row>

      <v-row>
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
                      border: 1.5px solid black;
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

      <v-row class="">
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
              v-for="i in 3"
              :key="i"
              :style="{ borderBottom: i != 3 ? '1px solid black' : '' }"
            >
              <v-expansion-panel-title
                expand-icon="mdi-menu-down"
                style="background-color: #eeeeee"
              >
                Item
              </v-expansion-panel-title>
              <v-expansion-panel-text
                >Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do
                eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut
                enim ad minim veniam, quis nostrud exercitation ullamco laboris
                nisi ut aliquip ex ea commodo consequat.</v-expansion-panel-text
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
let whatToExpect = ref([]);
let stats = ref([]);

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