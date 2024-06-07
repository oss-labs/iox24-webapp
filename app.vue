<template>
  <NuxtLayout>
    <v-app>
      <CoreAppToolbar />
      <CoreAppBanner />
      <v-main class="pa-0">
        <v-container fluid>
          <v-row justify="center" align="center">
            <v-col md="11" lg="10">
              <v-slide-y-reverse-transition>
                <div v-show="show">
                  <NuxtPage />
                </div>
              </v-slide-y-reverse-transition>
            </v-col>
          </v-row>
        </v-container>
      </v-main>
      <CoreAppFooter />
    </v-app>
  </NuxtLayout>
</template>

<script>
export default {
  data: () => ({
    show: false,
  }),
  created() {
    this.show = true;
  },
};
</script>
