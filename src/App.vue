<template>
  <div id="App">
    <img alt="photo" src="https://placehold.co/85x85" />
    <!--<HelloWorld msg="Welcome to Your Vue.js App" /> -->
    <h1>Animal Collect App</h1>
    <div class="container">
      <Animal-collector
        v-for="animal in collection"
        :key="animal.id"
        :collection="animal"
        @addCollection="collectAnimal"
      />
    </div>
  </div>
</template>

<script>
import AnimalCollector from "./components/animalCollector.vue";

export default {
  name: "App",
  data() {
    return {
      animalSelected: 0,
      animalSelectedAlbum: [],
      collection: [
        {
          id: 1,
          feature: "Hunter",
          photo: "https://placehold.co/95",
          habitat: "Mountain",
          animalName: "Puma",
          description:
            "Neque porro quisquam est qui dolorem ipsumquia dolor sit amet, consectetur, adipisci velit.",
          age: "23",
          weight: "95kg",
          measures: "180cm",
        },
        {
          id: 2,
          feature: "Fish",
          photo: "https://placehold.co/95",
          habitat: "Sea",
          animalName: "Angel",
          description:
            "Neque porro quisquam est qui dolorem ipsumquia dolor sit amet, consectetur, adipisci velit.",
          age: "3",
          weight: "350gr",
          measures: "12cm",
        },
        {
          id: 3,
          feature: "Bird",
          photo: "https://placehold.co/95",
          habitat: "Jungle",
          animalName: "Tucan",
          description:
            "Neque porro quisquam est qui dolorem ipsumquia dolor sit amet, consectetur, adipisci velit.",
          age: "8",
          weight: "2kg",
          measures: "32cm",
        },
      ],
    };
  },

  components: {
    AnimalCollector,
  },
  methods: {
    collectAnimal(id) {
      this.animalSelected++;
      this.animalSelectedAlbum.push(id);
      console.log("Animal collected!");
    },
  },
};
</script>

<style lang="scss">
#App {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  .container {
    width: 86%;
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 1em;
  }
}

.collection {
  background: rgb(145, 155, 155);
}

#btn2 {
  background: lightgreen;
  color: darkolivegreen;
}
</style>
