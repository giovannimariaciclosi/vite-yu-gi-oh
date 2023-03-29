<script>

import { store } from "../store.js";

export default {

  name: "CardItem",

  data() {
    return {

      store,

    }
  },

  props: {

    card: Object,

  },
}

</script>

<template>
  <div class="card">
    <div class="name">{{ card.name }}</div>
    <div class="type">{{ card.type }}</div>
    <img class="image" :src="card.card_images[0].image_url" alt="">
    <div class="desc">{{ card.desc }}</div>
    <div class="race">Race: {{ card.race }}</div>
    <div class="id">ID: {{ card.id }}</div>
    <div class="price">Market Price: <strong>{{ card.card_prices[0].cardmarket_price }} $</strong></div>

  </div>
</template>

<style lang="scss" scoped>
.card {
  display: flex;
  flex-direction: column;

  width: 300px;

  .name {
    font-weight: bold;
  }

  .type {
    font-style: italic;
  }

  .image {
    padding: .5em 0;
  }

  .desc {
    padding-top: 1em;
    font-size: .7em;
  }

  .race {
    font-size: .8em;
    font-weight: bold;
    padding-top: .2em;
  }

  .id {
    padding-top: .5em;
    font-size: .7em;
  }

  .price {
    text-align: center;
  }
}
</style>