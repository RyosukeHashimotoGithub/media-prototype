<template>
  <v-container fluid class="pa-0">
    <v-row class="text-center">
      <v-col class="mb-12">
        <first-view-carousel />
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
import FirstViewCarousel from "../organisms/FirstViewCarousel.vue";

export default {
  name: "FirstView",
  components: { FirstViewCarousel },
  data() {
    return {};
  },
};
</script>
