<template>
  <!-- <img alt="photo" src="https://placehold.co/150x150" />
  <HelloWorld msg="Welcome to Your Vue.js App" /> -->
  <h1>Animal Collect App</h1>
</template>

<script>
import animalCollector from "./components/animalCollector.vue";

export default {
  name: "AnimalCollector",
  components: {
    animalCollector,
  },
};
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
