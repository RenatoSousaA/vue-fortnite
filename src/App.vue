<template>
  <div id="app">
    <!-- <img alt="Vue logo" src="./assets/logo.png" /> -->
    <Tela />
  </div>
</template>

<script>
import Tela from "./components/Tela.vue";

export default {
  name: "app",
  components: {
    Tela
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #dadada;
  margin-top: 25px;
}

body {
  background-color: rgb(44, 44, 44);
}
</style>
