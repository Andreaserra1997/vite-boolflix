<script>
export default {
  props: {
    title: String,
    original_language: String,
    original_title: String,
    vote_averange: Number,
  },
};
</script>

<template>
  <div class="container">
    <div>Titolo: {{ title }}</div>
    <div>Lingua originale: {{ original_language }}</div>
    <div>Titolo Originale: {{ original_title }}</div>
    <div>Voto: {{ vote_averange }}</div>
  </div>
</template>

<style lang="scss" scoped>
.container {
  padding: 1rem;
}
</style>
