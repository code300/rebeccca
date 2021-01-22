<template>
  <div id="app">
    <Home />
  </div>
</template>

<script>
import Home from "./views/home";

export default {
  name: "App",
  components: {
    Home
  }
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #333;
  padding: 0;
  margin: 0;
  background-color: #f5f5f5;
  float: left;
  width: 100%;
  height: 100%;
}
</style>
