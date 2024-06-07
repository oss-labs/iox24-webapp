<template>
  <v-dialog max-width="700">
    <template v-slot:activator="{ props: activatorProps }">
      <div v-bind="activatorProps" style="cursor: pointer">
        <v-img
          src="https://io.google/2024/app/images/cs_program.webp"
          lazy-src="https://io.google/2024/app/images/cs_program.webp"
          style="border-radius: 20px; border: 1px solid black"
        ></v-img>
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
          <br>
          <CommonSocialBtn :links="data.social"/>
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

<style>
</style>