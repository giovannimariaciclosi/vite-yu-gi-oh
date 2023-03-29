<script>
import AppLoader from './components/AppLoader.vue';
import AppMain from './components/AppMain.vue';

import { store } from "./store";


export default {
  data() {
    return {

      store,

    };
  },
  components: { AppMain, AppLoader }
}

</script>

<template>
  <div>
    <AppMain></AppMain>
    <AppLoader v-if="store.isLoading"></AppLoader>
  </div>
</template>

<style lang="scss" scoped></style>
