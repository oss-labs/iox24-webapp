<template>
  <div class="mt-3">
    <v-btn
      class="mr-2"
      size="x-small"
      variant="tonal"
      v-if="links.linkedin != null && links.linkedin.length"
      :href="links.linkedin"
      target="_blank"
      icon="mdi-linkedin"
    ></v-btn>
    <v-btn
      class="mr-2"
      size="x-small"
      variant="tonal"
      target="_blank"
      v-if="links.github != null && links.github.length"
      :href="links.github"
      icon="mdi-github"
    ></v-btn>
    <v-btn
      class="mr-2"
      size="x-small"
      variant="tonal"
      v-if="links.web != null && links.web.length"
      :href="links.web"
      target="_blank"
      icon="mdi-web"
    ></v-btn>
    <v-btn
      class="mr-2"
      size="x-small"
      variant="tonal"
      v-if="links.twitter != null && links.twitter.length"
      :href="links.twitter"
      target="_blank"
      icon="mdi-twitter"
    ></v-btn>
  </div>
</template>

<script>
export default {
  props: ["links"],
};
</script>

<style>
</style>