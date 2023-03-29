<script>

export default {
  name: "AppHeader",
  data() {
    return {

    }
  },
}

</script>
  
<template>
  <div id="header-container">

    <img src="/img/logo.png" alt="logo">

    <h1>Yu-Gi-Ho API</h1>
  </div>
</template>

<style lang="scss" scoped>
#header-container {
  height: 100px;
  background-color: #f7f7f7;

  display: flex;
  align-items: center;
  gap: 30px;

  img {
    max-height: 100%;
  }

  h1 {
    color: black;
    font-size: 2.5em;
  }
}
</style>