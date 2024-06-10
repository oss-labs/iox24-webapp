<template>
  <v-dialog max-width="700">
    <template v-slot:activator="{ props: activatorProps }">
      <div
        v-bind="activatorProps"
        style="cursor: pointer"
        class="image-container"
      >
        <v-responsive :aspect-ratio="1 / 1">
          <v-img
            src="/assets/img/speakers/a.jpg"
            alt="Top Image"
            class="top-image"
            height="80%"
            width="100%"
            cover
            lazy-src="https://io.google/2024/app/images/cs_program.webp"
            style="border-radius: 20px"
          ></v-img>
        </v-responsive>
        <v-responsive :aspect-ratio="1 / 1">
          <v-img
            src="/assets/img/speakers/frame3.svg"
            alt="Bottom Image"
            class="bottom-image"
            cover
            lazy-src="https://io.google/2024/app/images/cs_program.webp"
            style="border-radius: 20px"
          ></v-img>
        </v-responsive>
      </div>
      <div class="info">
        <p class="mt-4" style="font-size: 120%; font-weight: 600">
          {{ data.name }}
        </p>
        <p>{{ data.meta.designation }}, {{ data.meta.company }}</p>
      </div>
    </template>

    <template v-slot:default="{ isActive }">
      <v-card rounded="xl">
        <v-card-text>
          <p class="mt-4" style="font-size: 120%; font-weight: 600">
            {{ data.name }}
          </p>
          <p>{{ data.meta.designation }}, {{ data.meta.company }}</p>

          <p class="mt-3"><b>Bio</b></p>
          {{ data.bio }}
          <br />
          <CommonSocialBtn :links="data.social" />
        </v-card-text>

        <v-card-actions>
          <v-spacer></v-spacer>
          <v-btn text="Close" @click="isActive.value = false"></v-btn>
        </v-card-actions>
      </v-card>
    </template>
  </v-dialog>
</template>

<script>
export default {
  props: ["data"],
};
</script>

<style scoped>
.image-container {
  position: relative;
  width: 100%;
  height: 200px; /* Adjust height as needed */
}
.v-responsive {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
}
.image-container .v-img {
  position: absolute;
  width: 100%;
  height: 100%;
  object-fit: cover;
}

.bottom-image {
  z-index: 3;
  transform: translate(0px, -2px);
}

.top-image {
  z-index: 4;
}

.info {
  padding: 10px;
  margin-top: 10px;
  margin-bottom: 5rem;
}
</style>
