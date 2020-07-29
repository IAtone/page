<template>
  <div id="app">
    <headers></headers>
    <router-view />
    <footers></footers>
    <!-- <tabs></tabs> -->
  </div>
</template>

<script>
import headers from "./components/header/header";
import footers from "./components/footer/footer";
export default {
  name: "App",
  components: {
    headers,
    footers
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
