<script>
import LangFlag from "vue-lang-code-flags/LangFlag.vue";

export default {
  props: {
    title: String,
    original_language: String,
    original_title: String,
    vote_average: Number,
    poster_path: String,
  },
  components: {
    LangFlag,
  },
  methods: {
    convertVote() {
      const stars = [];
      const rating = Math.round(this.vote_average * 5) / 10;
      for (let i = 0; i < 5; i++) {
        if (i < rating) {
          stars.push(true);
        } else {
          stars.push(false);
        }
      }
      return stars;
    },
  },
};
</script>

<template>
  <div class="container">
    <img
      :src="
        poster_path
          ? `https://image.tmdb.org/t/p/w342` + poster_path
          : './none.png'
      "
    />
    <div>Titolo: {{ title }}</div>
    <div>
      Lingua originale: <LangFlag :iso="original_language" :squared="false" />
      <span class="lang-text">{{ original_language }}</span>
    </div>
    <div>Titolo Originale: {{ original_title }}</div>
    <div>
      Voto:
      <span v-for="(star, index) in convertVote()" :key="index">
        <font-awesome-icon
          :icon="['fas', 'star']"
          :style="{ color: star ? 'yellow' : 'black' }"
        />
      </span>
    </div>
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
