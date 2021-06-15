<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <ListaDivisas titulo="Lista divisas!!!" />
  </div>
</template>

<script>
import ListaDivisas from "./components/ListaDivisas";

export default {
  name: 'App',
  components: {
    ListaDivisas
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
