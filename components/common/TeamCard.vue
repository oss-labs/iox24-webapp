<template>
  <v-dialog max-width="700">
    <template v-slot:activator="{ props: activatorProps }">
      <div v-bind="activatorProps" style="cursor: pointer" class="text-center">
        <v-avatar size="120">
          <v-img
            :src="`/team/${data.image}`"
            aspect-ratio="1/1"
            :lazy-src="`/team/${data.image}`"
            style="border-radius: 20px"
          ></v-img>
        </v-avatar>

        <div class="mt-3">
          <p class="mt-0 mb-0" style="font-size: 110%; font-weight: 600">
            {{ data.name }}
          </p>
          <p style="font-size: 90%">
            {{ data.meta.designation }}, {{ data.meta.company }}
          </p>
        </div>
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
</style>
