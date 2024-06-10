<template>
  <v-main class="">
    <v-container fluid class="pa-0 ma-0">
      <v-row class="Badge">
        <v-col md="7" cols="12" class="content--box pa-0 ma-0">
          <h2 class="text-h4">Badges</h2>
          <p>
            Now that you are here, how about personalising your DevFest India
            2023
            <br />
            profile? Upload an image and generate a personalised badge with the
            DevFest <br />India 2023 frame. Also share your image using
            #DevFestIndia on different <br />social platforms.
          </p>
          <h3 class="mt-5">Select Image</h3>
          <v-btn class="mt-4 mb-5 action_btn" rounded
            >Upload Image
            <v-icon>mdi-tray-arrow-up</v-icon>
          </v-btn>

          <p>
            *  We respect your privacy and are not storing your pictures on our
            servers.
          </p>
        </v-col>
        <v-col md="5" cols="12">
          <div class="grey-box">
            <v-img
              src="/assets/img/core/badge.svg"
              lazy-src="/assets/img/core/badge.svg"
              max-height="350"
              max-width="100%"
            ></v-img>
          </div>
        </v-col>
      </v-row>
    </v-container>
  </v-main>
</template>

<script>
export default {};
</script>

<style scoped>
.grey-box {
  background-color: #eeeeee;
  border-radius: 1rem;
  max-height: 100%;
  max-width: 60%;
  padding: 3rem 2rem;
}
.img_shape .v-img {
  display: flex;
  align-items: flex-start;
  justify-content: center;
}
.content--box {
  display: flex;
  align-items: flex-start;
  flex-direction: column;
  justify-content: center;
}
.action_btn {
  background: linear-gradient(90deg, #ffcb32, #34a853 80%);
  color: #000;
  box-shadow: none;
  border: 2px solid black;
}
</style>
