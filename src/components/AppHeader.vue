<script>
export default {
  data() {
    return {
      searchStr: "",
    };
  },
};
</script>

<template>
  <form @submit.prevent="$emit('searchRequest', searchStr)">
    <input type="text" v-model="searchStr" />
    <button>Cerca</button>
  </form>
</template>

<style></style>
