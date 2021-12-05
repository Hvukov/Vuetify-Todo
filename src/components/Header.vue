<template>
  <v-card class="overflow-hidden">
    <v-app-bar
      color="#43a047"
      dark
      prominent
      src="https://picsum.photos/1920/1080?random"
    >
      <template v-slot:img="{ props }">
        <v-img
          v-bind="props"
          gradient="to top right, rgba(55,236,186,.7), rgba(25,32,72,.7)"
        ></v-img>
      </template>

      <v-app-bar-title>My Todos!</v-app-bar-title>

      <v-spacer></v-spacer>

      <v-btn @click="toggleTheme" text rounded> Toggle Theme</v-btn>

      <!-- <v-btn icon>
              <v-icon>mdi-heart</v-icon>
            </v-btn>

            <v-btn icon>
              <v-icon>mdi-dots-vertical</v-icon>
            </v-btn> -->
    </v-app-bar>
  </v-card>
</template>

<script>
export default {
  methods: {
    toggleTheme() {
      this.$vuetify.theme.dark = !this.$vuetify.theme.dark;
    },
  },
};
</script>
