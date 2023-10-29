<template>
  <v-app>
    <NavBar />

    <v-spacer></v-spacer>

    <v-main>
    
      <router-view />
    </v-main>
  </v-app>
</template>

<script>
import NavBar from "./components/NavBar.vue";
export default {
  name: "App",
  components: {
    NavBar,
  },

  data: () => ({
    //
  }),
};
</script>

<style>
#title {
  padding: 20px;
  text-align: center;
}

</style>
