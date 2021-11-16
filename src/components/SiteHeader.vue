<template>
  <nav>
    <img
      class="logo_spotify"
      src="https://www.ore25.it/wp-content/uploads/2020/01/file-spotify-logo-png-4.png"
      alt=""
    />
    <div class="selection">
      <label class="select_genre" for="dischi">Seleziona un genere</label>
      <select class="generi" name="genere" id="genere">
        <option
          @click="$emit('selectgenre', selectString)"
          v-for="genre in genres"
          :key="genre"
          value="Tutti"
        >
          Tutti
        </option>
        <option value="Rock" v-for="genre in genres" :key="genre">Rock</option>
        <option value="Pop" v-for="genre in genres" :key="genre">Pop</option>
        <option value="Jazz" v-for="genre in genres" :key="genre">Jazz</option>
        <option value="Metal" v-for="genre in genres" :key="genre">
          Metal
        </option>
      </select>
    </div>
  </nav>
</template>

<script>
import axios from "axios";
export default {
  data() {
    const genres = ["Rock", "Pop", "Jazz", "Metal"];
    genres.forEach((element) => console.log(element));
  },
  mounted() {
    axios
      .get("https://flynn.boolean.careers/exercises/api/array/music")
      .then((r) => {
        this.cards = r.data.response;
        console.log(r.data);
      });
  },
  methods: {
    /* selectgenre(chooseGenre) {
      console.log(chooseGenre);
    }, */
  },
  computed: {
    /* takeFilteredGenre() {
      const filterGenre = this.cards.filter((card) => {
        return cards.genre(this.cards);
      });
    }, */
  },
};
</script>

<style lang="scss">
nav {
  height: 70px;
  background-color: #2e3a46;
  display: flex;
  align-items: center;
}
.logo_spotify {
  width: 50px;
  margin: 10px;
}
.select_genre {
  color: white;
  padding: 0.5rem;
}
.generi {
  width: 100px;
  padding: 0.1rem;
  border: 3px solid rgb(119, 119, 168);
  border-radius: 40px;
}
</style>
