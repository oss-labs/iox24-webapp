<template>
  <v-main>
    <v-img src="/assets/img/core/banner.png" cover>
      <div class="my-3 mt-4 text-center">
        Early birds registration started!
        <a
          :href="link"
          target="_blank"
          style="color: #2987f6; text-decoration: none"
          >Register Now</a
        >
      </div>
    </v-img>
  </v-main>
</template>

<script>
export default {
  props: ["link"],
};
</script>

<style>
</style>