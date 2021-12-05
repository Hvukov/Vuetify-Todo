<template>
  <v-app>
    <Header />
    <Todos />
    <Footer />
  </v-app>
</template>

<script>
import Footer from "./components/Footer.vue";
import Header from "./components/Header.vue";
import Todos from "./components/Todos.vue";

export default {
  name: "App",

  components: {
    Footer,
    Header,
    Todos,
  },

  data: () => ({
    //
  }),
};
</script>
