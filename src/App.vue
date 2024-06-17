<template>
  <div id="app">
    <FirstTitle></FirstTitle>
  </div>
</template>

<script>
import FirstTitle from "./components/FirstTitle.vue";
export default {
  name: "App",
  components: { FirstTitle },
};
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
