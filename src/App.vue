<script>
import AppHeader from "./components/AppHeader.vue";
import AppMain from "./components/AppMain.vue";
import { store } from "./store";
import axios from "axios";

export default {
  data() {
    return {
      store,
    };
  },
  components: {
    AppHeader,
    AppMain,
  },
  created() {
    axios
      .get(
        "https://api.themoviedb.org/3/search/movie?api_key=d1771cc21a27a7efbae55ba74eb3e374&query=all"
      )
      .then((response) => (this.store.arrFilm = response.data.results));
  },
};
</script>

<template>
  <AppHeader />
  <AppMain />
</template>

<style></style>
