<script>
import AppCard from "./AppCard.vue";
import { store } from "../store";

export default {
  data() {
    return {
      store,
    };
  },
  components: {
    AppCard,
  },
};
</script>

<template>
  <AppCard
    v-for="card in store.arrFilm"
    :key="card.id"
    :title="card.title"
    :original_language="card.original_language"
    :original_title="card.original_title"
    :vote_averange="card.vote_averange"
  />
</template>

<style></style>
