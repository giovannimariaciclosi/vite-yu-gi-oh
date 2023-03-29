<script>

import { store } from "../store.js";

import axios from "axios";

import CardItem from "./CardItem.vue";
import CardSearch from "./CardSearch.vue";


export default {
  name: "AppMain",
  data() {
    return {

      store,

    }
  },

  components: {
    CardItem,
    CardSearch
  },


  created() {

    axios.get(this.store.APIcall).then((res) => {
      // console.log(res.data.data);
      this.store.cards = res.data.data;

      this.store.isLoading = false;
      this.store.totalCardFound = this.store.cards.length;

    });
  },

  methods: {
    search() {
      let apiNewString = this.store.APIcall

      // https://db.ygoprodeck.com/api/v7/cardinfo.php?num=50&offset=0&name=dark magician

      if (this.store.cardName != "") {

        apiNewString += `&name=${this.store.cardName}`;

      }

      console.log(apiNewString);

      axios.get(apiNewString).then((res) => {

        console.log(res.data.data);

        this.store.cards = res.data.data;
        this.store.totalCardFound = this.store.cards.length;
      });
    },

  }
}


</script>
  
<template>
  <CardSearch @searchCard="search()"></CardSearch>
  <div id="cards-container">

    <!-- <div class="loading" v-if="store.cards.length != 0">LOADING...</div> -->
    <CardItem v-for="card in store.cards" :card="card">
    </CardItem>


  </div>
</template>

<style lang="scss" scoped>
#cards-container {
  display: flex;
  flex-flow: row wrap;
  justify-content: center;
  gap: 50px;
  padding-bottom: 2em;

  background-color: #d48f38;

  .loading {
    font-size: 2em;
  }

}
</style>