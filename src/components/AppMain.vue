<script>
import AppCard from "./AppCard.vue";
import AppCardTV from "./AppCardTV.vue";
import { store } from "../store";

export default {
  data() {
    return {
      store,
    };
  },
  components: {
    AppCard,
    AppCardTV,
  },
};
</script>

<template>
  <h2>Film</h2>
  <div class="container-film">
    <AppCard
      v-for="card in store.arrFilm"
      :key="card.id"
      :title="card.title"
      :original_language="card.original_language"
      :original_title="card.original_title"
      :vote_average="card.vote_average"
      :poster_path="card.poster_path"
    />
  </div>
  <h2>Serie TV</h2>
  <div class="container-tv">
    <AppCardTV
      v-for="cardtv in store.arrTV"
      :key="cardtv.id"
      :name="cardtv.name"
      :original_language="cardtv.original_language"
      :original_name="cardtv.original_name"
      :vote_average="cardtv.vote_average"
      :poster_path="cardtv.poster_path"
    />
  </div>
</template>

<style lang="scss" scoped>
.container-film,
.container-tv {
  display: flex;
  flex-wrap: wrap;
}
h2 {
  color: white;
}
</style>
