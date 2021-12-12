<template>
  <div id="app">
    <country-form />
  </div>
</template>

<script>
import CountryForm from "./components/CountryForm.vue";

export default {
  name: "App",
  components: {
    CountryForm,
  },
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
