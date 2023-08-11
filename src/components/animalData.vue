<template>
  <div class="collection">
    <div id="1" {{collection.feature}}></div>
    <div id="2">{{ collection.photo }}</div>
    <button>{{ collection.collected }}</button>
    <div id="4">{{ collection.photo }}</div>
    <div id="5">{{ collection.habitat }}</div>
    <div id="6">{{ collection.animalName }}</div>
    <div id="7">{{ collection.descrption }}</div>
    <div id="8">{{ collection.age }}</div>
    <div id="9">{{ collection.measures }}</div>
    <button>{{ collection.share }}</button>
  </div>
</template>

<script>
export default {
  name: "AnimalData",
  props: {
    collection: {
      type: Object,
      default() {
        return {
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
        };
      },
    },
  },
};
</script>
