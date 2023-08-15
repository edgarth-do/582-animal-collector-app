<template>
  <div id="App">
    <img alt="logo" src="./assets/logo.png" />
    <!-- <h1>Animal Collect App</h1> -->
    <div class="container">
      <AnimalData
        v-for="animal in collection"
        :key="animal.id"
        :collection="animal"
        @addCollection="collectAnimal"
        @share="shareAnimal"
      />
    </div>
  </div>
</template>

<script>
import AnimalData from "./components/animalData.vue";

export default {
  name: "App",
  data() {
    return {
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
          animalName: "Angel fish",
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
        {
          id: 4,
          feature: "Domestic",
          photo: "https://placehold.co/95",
          habitat: "Cities",
          animalName: "Cat",
          description:
            "Neque porro quisquam est qui dolorem ipsumquia dolor sit amet, consectetur, adipisci velit.",
          age: "7",
          weight: "4kg",
          measures: "50cm",
        },
        {
          id: 5,
          feature: "Pachyderm",
          photo: "https://placehold.co/95",
          habitat: "Jungle",
          animalName: "Elephant",
          description:
            "Neque porro quisquam est qui dolorem ipsumquia dolor sit amet, consectetur, adipisci velit.",
          age: "60",
          weight: "3400kg",
          measures: "3m",
        },
        {
          id: 6,
          feature: "Amphibian",
          photo: "https://placehold.co/95",
          habitat: "Stagnant water",
          animalName: "Frog common",
          description:
            "Neque porro quisquam est qui dolorem ipsumquia dolor sit amet, consectetur, adipisci velit.",
          age: "4",
          weight: "150g",
          measures: "28cm",
        },
      ],
    };
  },

  components: {
    AnimalData,
  },
  methods: {
    collectAnimal(id) {
      this.animalSelectedAlbum.push(id);
      console.log("Animal collected!");
    },
    shareAnimal(animalName) {
      console.log("Shared:", animalName);
    },
  },
};
</script>

<style scoped lang="scss">
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

#App {
  background-image: url(assets/tall-back-mobile.png);
  background-position: center;
  background-size: cover;
  font-family: "Marcellus", serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #ffffff;
  text-shadow: 1px 1px 3px #2c3e50;
  margin-top: 60px;
  img {
    max-width: 75%;
    height: auto;
    padding: 9px 16px;
  }
}

.container {
  width: 86%;
  margin: 0 auto;
  padding: 1.5em;
  display: grid;
  grid-template-columns: repeat(1, 1fr);
  gap: 2em;
  justify-content: center;
  align-items: center;
  border-radius: 9px;
  border: 3px solid rgba(214, 213, 213, 0.75);
  overflow: hidden;
}

.animalCollector {
  width: 100%;
  padding: 12px;
  background: rgba(107, 54, 47, 0.5);
  border: 4px whitesmoke solid;
  border-radius: 9px;
  justify-content: center;
  align-items: center;
}

@media screen and (min-width: 720px) {
  .container {
    grid-template-columns: repeat(2, 1fr);
  }
}

@media screen and (min-width: 1220px) {
  .container {
    grid-template-columns: repeat(3, 1fr);
  }
}
</style>
