<template>
  <v-app>
    <v-main class="custom-background">
      <TeamCo />
      <Carousel />
    </v-main>
  </v-app>
</template>

<script>
import TeamCo from "./components/Team-Co.vue";
import Carousel from "./components/Carousel.vue";

export default {
  name: "App",

  components: {
    TeamCo,
    Carousel,
  },

  data: () => ({
    //
  }),
};
</script>
<style>
.custom-background {
  background: linear-gradient(to right, #69e9ff, #00ff9d);
}
</style>
