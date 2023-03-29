<script>

import { store } from "../store.js";

export default {

  name: "CardSearch",

  data() {
    return {

      store,

    }
  },
}

</script>

<template>
  <div id="search">

    <input v-model="store.cardName" @keyup.enter="$emit('searchCard')" type="text"
      placeholder="Scrivi il nome di una carta">
    <button @click="$emit('searchCard')">Cerca</button>

  </div>

  <div id="total-cards">
    <span>Found {{ store.totalCardFound }} cards</span>
  </div>
</template>

<style lang="scss" scoped>
#search {
  text-align: center;
  padding: 20px;

  background-color: #d48f38;

  input {
    width: 300px;
    margin-right: 20px;
    background-color: white;
    border: transparent;
    height: 30px;
    padding-left: 20px;
    border-radius: 5px;
    color: black;
  }

  button {
    height: 30px;
    padding: 0 1em;
    border: transparent;
    border-radius: 5px;
    background-color: white;
    color: black;
  }
}

#total-cards {
  text-align: center;
  padding: 20px;
  background-color: #d48f38;
  padding-bottom: 4em;

  span {
    background-color: #242424;
    padding: 1em;
    border-radius: 10px;
  }
}
</style>