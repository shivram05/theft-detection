<template>
  <v-app>
    <NavBar />

    <v-main>
      <router-link to="prediction">

      </router-link>
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
};
</script>

<style>
#title {
  padding: 20px;
  text-align: center;
}

</style>
