<template>
  <div id="App">
    <img alt="logo" src="https://placehold.co/85x85" />
    <!--<HelloWorld msg="Welcome to Your Vue.js App" /> -->
    <h1>Animal Collect App</h1>
    <div class="container">
      <AnimalCollector
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
      ],
    };
  },

  components: {
    AnimalCollector,
  },
  methods: {
    collectAnimal(id) {
      this.animalSelectedAlbum.push(id);
      console.log("Animal collected!");
    },
  },
};
</script>

<style lang="scss">
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

@media screen and (max-width: 370px) {
  .container {
    width: 86%;
    margin: 0 auto;
    display: grid;
    grid-template-columns: repeat(1, 1fr);
    gap: 2em;
    justify-content: center;
    align-items: center;
    border-radius: 9px;
    border: 3px solid rgba(240, 128, 128, 0.5);
    overflow: hidden;
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
  }

  .collection {
    width: 86%;
    padding: 12px;
    background: rgba(107, 54, 47, 0.5);
    border: 4px whitesmoke solid;
    border-radius: 9px;
  }

  #div2 img {
    border-radius: 50px;
  }

  #btn,
  #btn2 {
    border-radius: 9px;
    padding: 7px 12px;
    &:hover {
      box-shadow: 1px 1px 4px #f9fadf;
    }
  }

  #btn {
    border: 1px solid rgb(185, 79, 17);
    background: rgb(238, 205, 144);
    color: rgb(107, 54, 47);
  }

  #btn2 {
    border: 1px solid darkolivegreen;
    background: lightgreen;
    color: darkolivegreen;
  }
}
@media screen and (max-width: 720px) {
  #App {
    background-image: url(assets/full-back-desktop.png);
    background-position: center;
    background-size: cover;
    font-family: "Marcellus", serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #ffffff;
    text-shadow: 1px 1px 3px #2c3e50;
    margin-top: 60px;
  }
  .container {
    width: 86%;
    margin: 0 auto;
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 2em;
    justify-content: center;
    align-items: center;
    border-radius: 9px;
    border: 3px solid rgba(240, 128, 128, 0.5);
  }
}

@media screen and (max-width: 1220px) {
  #App {
    background-image: url(assets/full-back-desktop.png);
    background-position: center;
    background-size: cover;
    font-family: "Marcellus", serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #ffffff;
    text-shadow: 1px 1px 3px #2c3e50;
    margin-top: 60px;
  }
  .container {
    width: 86%;
    margin: 0 auto;
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 2em;
    justify-content: center;
    align-items: center;
    border-radius: 9px;
    border: 3px solid rgba(240, 128, 128, 0.5);
  }
}
</style>
