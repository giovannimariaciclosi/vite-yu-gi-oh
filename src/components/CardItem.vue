<script>

export default {

  name: "CardItem",

  data() {
    return {
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
    <div class="desc">{{ card.desc }}</div>
    <div class="race">{{ card.race }}</div>


    <!-- <div class="image">{{ card.card_images }}</div> -->
    <!-- <img :src="card.card_images" alt=""> -->
  </div>
</template>

<style lang="scss" scoped>
.card {
  display: flex;
  flex-direction: column;

  width: 400px;

  .name {
    font-weight: bold;
  }

  .type {
    font-style: italic;
  }

  .desc {
    padding-top: 1em;
    font-size: .7em;
  }

  .race {
    font-size: .8em;
    font-weight: bold;
    padding-top: .5em;
  }
}
</style>