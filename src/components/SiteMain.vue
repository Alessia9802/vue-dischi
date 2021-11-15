<template>
  <div>
    <div
      class="container"
      v-for="card in cards"
      :key="card.poster"
      :title="card.title"
      :author="card.author"
      :genre="card.genre"
      :year="card.year"
    >
      {{ card.poster }}{{ card.title }}{{ card.author }}{{ card.genre }}
      {{ card.year }}
    </div>
  </div>
</template>

<script>
import axios from "axios";

export default {
  props: {
    key: String,
    title: String,
    author: String,
    genre: String,
    year: String,
  },
  data() {
    return {
      cards: [],
    };
  },

  mounted() {
    axios
      .get("https://flynn.boolean.careers/exercises/api/array/music")
      .then((r) => {
        this.cards = r.data;
        console.log(r.data);
      });
  },
};
</script>

<style lang="scss">
.container {
  background-color: #1e2d3b;
  height: 1000px;
}
</style>
