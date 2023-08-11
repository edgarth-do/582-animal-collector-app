<template>
  <img alt="photo" src="https://placehold.co/85x85" />
  <!--<HelloWorld msg="Welcome to Your Vue.js App" /> -->
  <h1>Animal Collect App</h1>
</template>

<script>
import animalCollector from "./components/animalCollector.vue";

export default {
  name: "Album",
  data() {
    return {
      animalSelected: 0,
      animalSelectedAlbum: [],
      collection: [
        {
          id: 1,
          feature: "Hunt",
          photo: "https://placehold.co/185*185",
          habitat: "Mountain",
          animalName: "Puma",
          description:
            "Neque porro quisquam est qui dolorem ipsumquia dolor sit amet, consectetur, adipisci velit.",
          age: "23",
          weight: "95kg / 150lb",
          measures: "180cm / 6ft",
        },
      ],
    };
  },

  components: {
    animalCollector,
  },
  methods: {
    addCollection(id) {
      this.collection++;
      console.log([], "animal collected!");
    },
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
