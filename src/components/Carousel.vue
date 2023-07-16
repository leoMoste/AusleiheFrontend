<template>
  <div class="d-flex align-center flex-column pa-6">
    <v-card width="70%">
      <v-carousel>
        <v-carousel-item src="../assets/Books.jpg" cover></v-carousel-item>

        <v-carousel-item
          src="../assets/LaptopMedium.jpg"
          cover
        ></v-carousel-item>
        <v-carousel-item
          src="../assets/TabletMedium.jpg"
          cover
        ></v-carousel-item>
        <v-carousel-item src="../assets/cars.jpg" cover></v-carousel-item>
        <v-carousel-item src="../assets/money.jpg" cover></v-carousel-item>
        <v-carousel-item src="../assets/Gold.jpg" cover></v-carousel-item>
      </v-carousel>
    </v-card>
  </div>
</template>

<script>
export default {
  name: "App",

  components: {},

  data: () => ({
    //
  }),
};
</script>
<style></style>
