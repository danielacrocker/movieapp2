<template>
  <v-app class="grey">
    <nav-bar>

    </nav-bar>
    <!-- <v-app-bar app color="primary" dark></v-app-bar> -->

    <v-content>
      <p>App content</p>
      <router-view></router-view>
    </v-content>
  </v-app>
</template>

<script>
// import HelloWorld from "./components/HelloWorld";
import NavBar from '@/components/Navbar.vue';
import "./assets/stylesheets/main.css";

export default {
  name: "App",

  components: {
    // HelloWorld
    navBar: NavBar,
  },

  data: () => ({})
};
</script>

<style scoped>
#app  {
  color: blue;
}
</style>
