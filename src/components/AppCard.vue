<script>
export default {
  props: {
    title: String,
    original_language: String,
    original_title: String,
    vote_average: Number,
    poster_path: String,
  },
};
</script>

<template>
  <div class="container">
    <img :src="`https://image.tmdb.org/t/p/w342` + poster_path" />
    <div>Titolo: {{ title }}</div>
    <div>Lingua originale: {{ original_language }}</div>
    <div>Titolo Originale: {{ original_title }}</div>
    <div>Voto: {{ vote_average }}</div>
  </div>
</template>

<style lang="scss" scoped>
.container {
  padding: 1rem;
}
</style>
