<template>
  <div>
    <div class="container">
      <div class="card" v-for="card in cards" :key="card.title">
        <div class="album">
          <img :src="card.poster" alt="" />
        </div>
        <div class="title_song">
          {{ card.title }}
        </div>
        <div class="name_author">
          {{ card.author }}
        </div>
        <!-- <div class="song_genre">
          {{ card.genre }}
        </div> -->
        <div class="song_year">
          {{ card.year }}
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import axios from "axios";

export default {
  data() {
    return {
      cards: [],
    };
  },

  mounted() {
    axios
      .get("https://flynn.boolean.careers/exercises/api/array/music")
      .then((r) => {
        this.cards = r.data.response;
        console.log(r.data);
      });
  },
};
</script>

<style lang="scss">
.container {
  background-color: #1e2d3b;
  height: 700px;
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  align-items: center;
}

.card {
  width: 150px;
  height: 300px;
  background-color: #2e3a46;
  margin: 1.5rem;
  text-align: center;
  /* padding: 0.5rem; */
}

.album img {
  width: 150px;
  padding: 1rem;
}

.title_song {
  color: white;
  text-transform: uppercase;
  font-weight: 700px;
  padding-bottom: 0.5rem;
}
.song_year,
.name_author {
  color: #808080;
}
</style>
