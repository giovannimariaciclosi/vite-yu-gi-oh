<script>

export default {
  name: "AppLoader",

  data() {
    return {
    }
  },
}
</script>

<template>
  <div id="loader">

    Loading Cards...

  </div>
</template>

<style lang="scss" scoped>
#loader {
  display: flex;
  justify-content: center;
  align-items: center;
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: black;
}
</style>