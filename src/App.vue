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
  methods: {
    requestFilm(searchStr) {
      axios
        .get("https://api.themoviedb.org/3/search/movie", {
          params: {
            api_key: "d1771cc21a27a7efbae55ba74eb3e374",
            query: searchStr,
          },
        })
        .then((response) => (this.store.arrFilm = response.data.results));
      axios
        .get("https://api.themoviedb.org/3/search/tv", {
          params: {
            api_key: "d1771cc21a27a7efbae55ba74eb3e374",
            query: searchStr,
          },
        })
        .then((response) => (this.store.arrTV = response.data.results));
    },
  },
};
</script>

<template>
  <AppHeader @searchRequest="requestFilm" />
  <AppMain />
</template>

<style></style>
