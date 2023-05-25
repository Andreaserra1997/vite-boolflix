<script>
export default {
  props: {
    name: String,
    original_language: String,
    original_name: String,
    vote_average: Number,
    poster_path: String,
  },
};
</script>

<template>
  <div class="container">
    <img :src="'https://image.tmdb.org/t/p/' + poster_path" />
    <div>Titolo: {{ name }}</div>
    <div>Lingua originale: {{ original_language }}</div>
    <div>Titolo Originale: {{ original_name }}</div>
    <div>Voto: {{ vote_average }}</div>
  </div>
</template>

<style lang="scss" scoped>
.container {
  padding: 1rem;
}
</style>
