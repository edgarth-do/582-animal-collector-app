<template>
  <h2>Animal Collector app</h2>
  <animalData> </animalData>
</template>

<script>
import collection from "./animalData.vue";

export default {
  name: "animalName",
  props: {
    type: Array,
    default() {
      return [];
    },
  },
  components: {
    animalName,
  },
  methods: {
    addCollection(id) {
      console.log("Already collected...", id + animalName);
    },
  },
};
</script>
