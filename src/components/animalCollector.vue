<template>
  <h2>Animal Collector app</h2>
  <animalData :collection="defaultCollection"> </animalData>
</template>

<script>
import AnimalData from "./animalData.vue";

export default {
  name: "animalCollector",
  components: {
    AnimalData,
  },
  data() {
    return {
      defaultCollection: [
        {
          id: 1,
          feature: "feature",
          photo: "https://placehold.co/185*185",
          habitat: "habitat",
          animalName: "animalName",
          description:
            "Neque porro quisquam est qui dolorem ipsumquia dolor sit amet, consectetur, adipisci velit.",
          age: 0,
          weight: "weight",
          measures: "measures",
          share: "Share",
        },
      ],
    };
  },
  methods: {
    addCollection(id, animalName) {
      console.log("Already collected...", id, animalName);
    },
  },
};
</script>
