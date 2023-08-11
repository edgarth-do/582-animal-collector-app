<template>
  <h2>Animal Collector app</h2>
  <animalData
    v-model:$data="defaultCollection"
    :collection="defaultCollection"
    :id="data.animalName"
    :feature="data.feature"
  ></animalData>
</template>

<script>
import AnimalData from "./animalData.vue";

export default {
  name: "animalCollector",
  props: {
    collection: {
      type: Array,
      default() {
        return [];
      },

      id: {
        type: Number,
        required: true,
      },

      feature: {
        type: String,
        required: true,
      },

      photo: {
        type: Image,
        required: true,
      },
      habitat: {
        type: String,
        required: true,
      },

      animalName: {
        type: String,
        required: true,
      },

      description: {
        type: String,
        required: true,
      },

      age: {
        type: String,
        required: true,
      },

      weight: {
        type: String,
        required: true,
      },

      measures: {
        type: String,
        required: true,
      },
    },
  },
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

<style scoped lang="scss">
.collection {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  grid-template-rows: repeat(5, 1fr);
  grid-column-gap: 12px;
  grid-row-gap: 12px;
}

#div1 {
  grid-area: 1 / 1 / 3 / 2;
}
#div2 {
  grid-area: 1 / 2 / 3 / 4;
}
#btn3 {
  grid-area: 1 / 4 / 2 / 5;
}
#div4 {
  grid-area: 2 / 4 / 3 / 5;
}
#div5 {
  grid-area: 3 / 1 / 4 / 5;
}
#div6 {
  grid-area: 4 / 1 / 5 / 5;
}
#div7 {
  grid-area: 5 / 1 / 6 / 2;
}
#div8 {
  grid-area: 5 / 2 / 6 / 3;
}
#div9 {
  grid-area: 5 / 3 / 6 / 4;
}
#btn2 {
  grid-area: 5 / 4 / 6 / 5;
}
</style>
