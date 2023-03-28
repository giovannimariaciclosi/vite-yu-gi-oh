<script>

import { store } from "../store.js";

import axios from "axios";

import CardItem from "./CardItem.vue";


export default {
  name: "AppMain",
  data() {
    return {

      store,

    }
  },

  components: {

    CardItem,

  },
  created() {

    axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=50&offset=0').then((res) => {
      // console.log(res.data.data);
      this.store.cards = res.data.data;
    });

  },
}

</script>
  
<template>
  <h1>Your Deck:</h1>
  <div id="cards-container">

    <div class="loading" v-if="store.cards.length < 50">LOADING...</div>
    <CardItem v-for="card in store.cards" :card="card" v-else>
    </CardItem>


  </div>
</template>

<style lang="scss" scoped>
h1 {
  padding: 2em;
  text-align: center;
}

#cards-container {
  display: flex;
  flex-flow: row wrap;
  justify-content: center;
  gap: 50px;

  .loading {
    font-size: 2em;
  }

}
</style>