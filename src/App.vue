<script>
import AppHeader from './components/AppHeader.vue';
import AppLoader from './components/AppLoader.vue';
import AppMain from './components/AppMain.vue';

import { store } from "./store";


export default {
  data() {
    return {

      store,

    };
  },
  components: { AppMain, AppLoader, AppHeader }
}

</script>

<template>
  <div>
    <AppHeader></AppHeader>
    <AppMain></AppMain>
    <AppLoader v-if="store.isLoading"></AppLoader>
  </div>
</template>

<style lang="scss" scoped></style>
