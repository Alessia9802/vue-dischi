<template>
  <div class="container" v-for="card in cards"></div>
</template>

<script>
import axios from "axios";

export default {
  data() {
    return {
      cards: [],
    };
  },
};

mounted(){
  axios
    .get("https://flynn.boolean.careers/exercises/api/array/music")
    .then((r) => {
      this.cards = r.data;
      console.log(r.data);
    });
}
</script>

<style lang="scss">
.container {
  background-color: #1e2d3b;
  height: 1000px;
}
</style>
