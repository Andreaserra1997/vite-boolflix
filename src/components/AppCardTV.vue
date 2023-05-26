<script>
import LangFlag from "vue-lang-code-flags/LangFlag.vue";

export default {
  props: {
    name: String,
    original_language: String,
    original_name: String,
    vote_average: Number,
    poster_path: String,
  },
  components: {
    LangFlag,
  },
  methods: {
    convertVote() {
      return Math.round(this.vote_average * 5) / 10;
    },
  },
};
</script>

<template>
  <div class="container">
    <img :src="'https://image.tmdb.org/t/p/w342' + poster_path" />
    <div>Titolo: {{ name }}</div>
    <div>
      Lingua originale: <LangFlag :iso="original_language" :squared="false" />
      <span class="lang-text">{{ original_language }}</span>
    </div>
    <div>Titolo Originale: {{ original_name }}</div>
    <div>Voto: {{ convertVote() }}</div>
  </div>
</template>

<style lang="scss" scoped>
.container {
  padding: 1rem;
}
.flag-icon-undefined {
  display: none;
}
.flag-icon-undefined + .lang-text {
  display: inline;
}
.lang-text {
  display: none;
}
</style>
