<template>
  <v-app>
    <v-app-bar app dark>
      <div class="d-flex align-center">
        <v-img
          alt="Vuetify Logo"
          class="shrink mr-2"
          contain
          src="https://cdn.vuetifyjs.com/images/logos/vuetify-logo-dark.png"
          transition="scale-transition"
          width="40"
        />

        media-prototype
      </div>

      <v-spacer></v-spacer>

      <v-btn text>
        <span class="mr-2">閲覧履歴</span>
        <v-icon>mdi-open-in-new</v-icon>
      </v-btn>
    </v-app-bar>

    <v-main>
      <FirstView />
    </v-main>
  </v-app>
</template>

<script>
import FirstView from "./components/pages/FirstView";

export default {
  name: "App",

  components: {
    FirstView,
  },

  data: () => ({
    //
  }),
};
</script>
