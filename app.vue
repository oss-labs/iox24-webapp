<template>
  <NuxtLayout>
    <v-app>
      <CoreAppToolbar />
      <v-main class="pa-0">
        <v-container fluid>
          <v-row justify="center" align="center">
            <v-col md="11" lg="10">
              <v-slide-y-reverse-transition>
                <NuxtPage v-show="show" />
              </v-slide-y-reverse-transition>
            </v-col>
          </v-row>
        </v-container>
      </v-main>
      <CoreAppFooter />
    </v-app>
  </NuxtLayout>
</template>

<script setup>
let show = ref(false);

onBeforeUpdate(() => {
  show.value = true; // <div>
});
</script>
