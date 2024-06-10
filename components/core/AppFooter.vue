<template>
  <v-main class="pa-0">
    <v-container
      fluid
      class="footer"
      style="background-color: #202124; color: white !important"
    >
      <v-row>
        <v-col md="2" cols="12">
          <p class="mb-0" style="font-size: 120%">Google IO Extended 24</p>
        </v-col>
        <v-col md="8" cols="12">
          <a
            href="https://developers.google.com/community-guidelines"
            target="_blank"
            style="color: #9aa09e; text-decoration: none"
            class="mb-0 mr-6"
            >Community Guidelines</a
          >
          <br class="d-md-none" />
          <a
            href="https://gdg.community.dev/participation-terms/"
            target="_blank"
            style="color: #9aa09e; text-decoration: none"
            class="mb-0"
            >Participations Terms</a
          >
        </v-col>
        <v-col md="2" style="color: #9aa09e">
          <a
            href="https://gdg.community.dev/participation-terms/"
            target="_blank"
            style="color: #9aa09e; text-decoration: none; font-size: 80%"
            class="mb-0"
            >Developed by Open Sources Labs</a
          >
        </v-col>
      </v-row>
    </v-container>
  </v-main>
  <!-- <v-footer
    style="background-color: #202124; color: white !important"
    class="pa-0"
  >
  v-
    <div class="d-flex align-center py-5 px-4 ">
      <div class="mr-5 flex-md-column">
        <p class="mb-0" style="font-size: 120%">Google IO Extended</p>
      </div>
      <div class="flex-md-column">
        <a href="https://developers.google.com/community-guidelines" target="_blank" style="color: #9AA09E;text-decoration: none;" class="mb-0">Community Guidelines</a>
        <a href="https://developers.google.com/community-guidelines" target="_blank" style="color: #9AA09E;text-decoration: none;" class="mb-0">Community Guidelines</a>
      </div>
    </div>
  </v-footer> -->
</template>

<script>
export default {};
</script>

<style>
.footer {
  position: absolute;
  bottom: 0;
}
</style>
