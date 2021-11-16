<template>
  <nav>
    <img
      class="logo_spotify"
      src="https://www.ore25.it/wp-content/uploads/2020/01/file-spotify-logo-png-4.png"
      alt=""
    />
    <div class="selection">
      <label class="select_genre" for="dischi">Seleziona un genere</label>
      <select
        class="generi"
        name="genere"
        id="genere"
        v-for="genre in genres"
        :key="genre"
      >
        <option @click="$emit('selectgenre', selectString)" value="Tutti">
          Tutti
        </option>
        <option value="Rock">Rock</option>
        <option value="Pop">Pop</option>
        <option value="Jazz">Jazz</option>
        <option value="Metal">Metal</option>
      </select>
    </div>
  </nav>
</template>

<script>
export default {
  data() {
    const genres = ["Rock", "Pop", "Jazz", "Metal"];
    console.log(genres);
    return {
      /* selectString: "", */
    };
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
